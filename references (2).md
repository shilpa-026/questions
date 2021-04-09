# Datalab API Test Automation

This project contains the framework used to automate GBI Datalab UI and API testing. The framework is built on Robot Framework, an existing, open-source, Python-based framework for test and robotic process automation. This document contains a brief overview of the project; for a more detailed explanation, see the QA subsection of the Datalab documentation.

## Installation and Setup

To install, first download or clone the git repository. Then, in the `datalab-automation` folder, run the following commands:

```commandline
python3 -m venv env
. env/bin/activate
pip install -r requirements.txt
```

This will create and activate a virtual environment for the framework to run in, and install the required packages and dependencies in that virtual environment.

The API test cases have a separate installation script. From the `datalab-automation` folder, run the following commands:
```commandline
cd api_test_cases
make install
```
This will install the necessary components of the API test scripts, as well as any dependencies.

The next step is to open `config.yaml` in the `meta_data` folder, and input your secret key, username and password. These credentials will be
used to log into Datalab in the browser launched by the framework. Optionally, you can use the system account credentials already provided in the `config.yaml` file.

You can optionally install a PyCharm plugin to format .robot files, and make them easier to read. The name of the plugin is: Intellibot @SeleniumLibrary Patched.

## Running API Test Cases

### Running functional tests

To run the functional tests, first navigate to the folder `api_test_cases/functional_tests` in the terminal. Then run the following command
``` commandline
robot --include <tagname> .
```
The `<tagname>` specifies the component to run. The allowed options are: `Flows`, `Notebooks`, `Jobs`, `Project`, `Visualize`, and `Wrangler`. Optionally, to run all the test cases you can provide the tag `regression`.

### Running load tests

There are two ways to run the load tests: with and without performance threshold validation.

#### Running without performance threshold validation

To run the load tests without validating against performance thresholds, first open `run.py` in the `load_tests` directory. The `run.py` file looks like this:

```python
from load_tests.notebooks import NotebookUser
from load_tests.projects import ProjectUser
from load_tests.jobs import JobsUser
from load_tests.Visualize import VisualizeUser
from load_tests.Wrangler import WranglerUser
from load_tests.Flows import FlowUser
import locust_plugins
```

Comment out the components that you do not want to run, so that only the components that you want to run are imported. Then navigate in your terminal to the `api_test_cases` directory. From there, run the following command:

```commandline
make run_load_tests
```

This will launch a Locust web interface at `http://0.0.0.0:8089`, which you can use to specify the inputs, control the tests, and observe the output.

#### Running with performance threshold validation

To run the load tests with performance threshold validation, start by specifying the components you want to test in `api_performance_validation.robot`. This file is located under the `load_tests_robot_integration` subfolder of the `load_tests` directory. There are six component User classes:

- NotebookUser
- JobsUser
- FlowUser
- VisualizeUser
- WranglerUser
- ProjectUser

The components to run should be given in the `${USER_CLASSES}` variable of `api_performance_validation.robot`, separated by one space.

Then specify the report name and local path (relative to `api_test_cases`) in the `${REPORT_PATH}` variable. Specify the parameters to pass to Locust (host, number of users, spawn rate, etc.) in the remaining variables.

The reporting options available are CSV and HTML; they should be specified in the `${REPORTING_OPTIONS}` variable, with one separating space. Note that CSV reporting is required to validate against the specified thresholds.

Finally, navigate to the `api_test_cases` directory and run the following command:

```commandline
robot --include <component_tag> load_tests/load_tests_robot_integration/api_performance_validation.robot
```

Specify the components to test in the `<component_tag>` option above. There are six options:
- notebook
- jobs
- project
- flows
- visualize
- wrangler

For each component that is tested, add a separate `--include <component_tag>` option. For example, if Locust is testing NotebookUser and FlowUser:
```commandline
robot --include notebook --include flows load_tests/load_tests_robot_integration/api_performance_validation.robot
```

## Project Structure

This project is divided into six sections:

1. API Test Cases
2. Metadata
3. Page locators
4. Page objects
5. Resource files
6. Utility files

Each section will be explained below.

### API Test Cases

The `api_test_cases` folder contains the functional and non-functional API test cases, as well as related setup and configuration files.

The `functional_tests` subfolder contains functional tests organized by Datalab component, and related files. The `Datalab_Cookie` subfolder contains files required to extract the cookies for a Datalab session, while the `json_body` subfolder contains the payloads for the API POST requests. The `credentials.yaml` file contains configuration parameters for the functional tests.

The `load_tests` subfolder contains the load testing scripts. Its `load_tests_robot_integration` subfolder contains files for validating API performance against user-defined thresholds.

### Metadata

The `meta_data` folder contains configuration files for login and test case execution. The `config.yaml` file contains the credentials used for logging into Datalab; this is the same file mentioned in the [Getting Started](#getting-started) section.

### Page locators

The `page_locators` folder consists of `.yaml` files with the XPath expressions used for identifying the various Datalab page elements. These `.yaml` files are organized by component. The `.py` files in this folder are variable files used by Robot Framework to import the XPath expressions into the test cases.

### Page objects

The `page_objects` folder consists of Robot Framework resource files for performing various tasks in the Datalab components. They are organized by component, and provide the keywords used by the test cases.

### Resource files

The `resources` folder contains Robot Framework files required to set up the browser environment. The `chrome_driver.robot` file contains the keywords used to open the browser with different capabilities, including headless mode. The `set_up.robot` file contains the higher-level keywords used to log into Datalab.

### Utility files

The `utils` folder contains the web drivers used to interact with the browser, as well as auxiliary Python scripts used throughout the application.

## References

### Libraries used in API Functional tests


|RequestsLibrary|https://marketsquare.github.io/robotframework-requests/doc/RequestsLibrary.html|Below are the keywords used from this library <br> 1.Create Session <br> 2.GET On Session <br> 3.POST On Session <br> 4.PUT On Session  <br> 5.PATCH On Session <br> 6.DELETE On Session |
|OperatingSystem |https://robotframework.org/robotframework/latest/libraries/OperatingSystem.html| Below are the keywords used from this library <br> 1.Get File <br> 2.Create Directory <br> 3.Create File|
|Collections|https://robotframework.org/robotframework/latest/libraries/Collections.html|Below are the keywords used from this library <br> 1.Get From Dictionary <br> 2.Get From List <br> 3.Create File|
|BuiltIn|https://robotframework.org/robotframework/latest/libraries/BuiltIn.html|Below are the keywords used from this library <br> 1.Catenate <br> 2.Convert To Integer <br> 3.Convert To String <br> 4.Create Dictionary <br> 5.Evaluate <br> 6.Log To Console <br> 7.Set Global Variable <br> 8.Should Be Equal |
|JSONLibrary|https://robotframework-thailand.github.io/robotframework-jsonlibrary/JSONLibrary.html|Below are the keywords used from this library <br> 1.Load JSON From File <br> 2.Update Value To Json <br> 3.Get Value From Json|
|String|https://robotframework.org/robotframework/latest/libraries/String.html|Below are the keywords used from this library <br> 1.Generate Random String |



