
# Welcome to your CDK Python project!

This is a blank project for CDK development with Python.

The `cdk.json` file tells the CDK Toolkit how to execute your app.

This project is set up like a standard Python project.  The initialization
process also creates a virtualenv within this project, stored under the `.venv`
directory.  To create the virtualenv it assumes that there is a `python3`
(or `python` for Windows) executable in your path with access to the `venv`
package. If for any reason the automatic creation of the virtualenv fails,
you can create the virtualenv manually.

## Installation

This project uses [uv](https://docs.astral.sh/uv/) for Python dependency management, which provides fast and reliable package installation.

First, ensure uv is installed on your system:

```
$ pip install uv
```

or

```
$ curl -LsSf https://astral.sh/uv/install.sh | sh
```

Once uv is installed, you can install all dependencies and create a virtual environment in one step:

```
$ uv sync
```

This will automatically create a virtual environment and install all project dependencies defined in `pyproject.toml`.

To activate the virtual environment created by uv:

```
$ source .venv/bin/activate
```

On Windows:

```
% .venv\Scripts\activate.bat
```

Next, install the AWS CDK CLI and libraries **locally within the project** (not globally). This ensures version consistency and allows different CDK versions across projects:

```
$ npm install
```

This will install the CDK CLI specified in `package.json` into the local `node_modules` directory. You can then run CDK commands using the `npx` prefix, which automatically uses the locally installed version.

To add additional dependencies, for example other CDK libraries, simply add them to the `dependencies` array in `pyproject.toml` and run:

```
$ uv sync
```

For development dependencies like testing tools, add them to the `dev-dependencies` section under `[tool.uv]` in `pyproject.toml`.

## Architecture

This CDK application deploys the following infrastructure:

### Backend Stack

The Backend stack (`backend/component.py`) currently serves as a template foundation with no active resources deployed. The stack includes:

- **Stack Definition**: A basic CDK Stack construct that can be extended with AWS resources
- **Template Structure**: Commented example code showing how to add resources (e.g., SQS Queue)

This is a starter template designed to be customized with your specific infrastructure requirements. Resources can be added by uncommenting and modifying the example code or by adding new AWS service constructs from the `aws_cdk` library.

## Useful commands

At this point you can now synthesize the CloudFormation template for this code.

```
$ npx cdk synth
```

Additional useful commands (note the `npx` prefix to use the locally installed CDK):

 * `npx cdk ls`          list all stacks in the app
 * `npx cdk synth`       emits the synthesized CloudFormation template
 * `npx cdk deploy`      deploy this stack to your default AWS account/region
 * `npx cdk diff`        compare deployed stack with current state
 * `npx cdk docs`        open CDK documentation

Enjoy!
