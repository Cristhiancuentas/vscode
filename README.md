# RAW Labs VS Code extension README

## Table of Contents
- [Features](#features)
- [Requirements](#requirements)
- [Usage](#usage)
	- [Installation](#installation)
	- [Layout](#layout)
	- [Authentication](#authentication)
		- [Login](#Login)
		- [Logout](#logout)
	- [Invoking Snippets](#invoking-snippets)
	- [Yaml auto-completion and validation](#yaml-auto-completion-and-validation)
	- [RQL validation](#rql-validation)
	- [Running Yaml files](#running-yaml-files)
		-[Endpoints without arguments](#endpoints-without-arguments)
		-[Endpoints with arguments](#endpoints-with-arguments)
	- [Listing Data Sources and Test Access](#listing-data-sources-and-test-access)
	- [Scratchpad](#scratchpad)
		- [Opening](#opening)
		- [Running Code](#running-code)
- [Extension Settings](#extension-settings)
	- [Environment Setting](#environment-setting)
- [Known Issues](#known-issues)
- [Release Notes](#release-notes)


## Features
- RQL
	- Syntax highlighting
	- Errors underlining after execution
	- Basic snippets
	- Scratchpad
	- Documentation on Hover
	- Autocompletion
- YAML
	- RAW Yaml files execution
	- RAW Yaml files snippets
	- Validation through RAW yaml schema
	- Auto-completion through RAW yaml schema
- Data Sources
	- List Data Sources
	- Test Access
  

## Requirements

Until adding extension pack on marketplace, the dependencies have to be installed manually. So before using the extension please install the below extensions manually from VS Code extensions panel tab:

- [Excel Viewer](https://marketplace.visualstudio.com/items?itemName=GrapeCity.gc-excelviewer)
- [YAML](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml)

## Usage

### Installation

// TO DO add image and url of the extension

### Layout

![Layout](https://github.com/raw-labs/vscode/tree/main/imagesextension-layout.png)

### Authentication

#### Login

When trying to Login, or run yaml file without being Logged In, a pop up will emerge where you have to provide your access token. The token expires after 24 hours.

![Provide Token](https://github.com/raw-labs/vscode/tree/main/imagesprovide-token.png)

#### Logout
In order to logout, go to the left bottom corner of the editor, select the `Accounts` icon and then sign out.

![Logout](https://github.com/raw-labs/vscode/tree/main/imageslogout.png)

### Invoking Snippets
While editing YAML and RQL files press `ctl + space`, a list will emerge with the available options.

![YAML Snippets](https://github.com/raw-labs/vscode/tree/main/imagesyaml-snipets.png)

### Yaml auto-completion and validation
In order to use auto-completion and validation for Yaml file, you have to add the schema for the specific RAW yaml file (site or endpoint). Type `raw-import-{site,endpoint}-schema` and press enter and the schema will be injected.

Apart from that you can generate all the needed fields directly by typing:
- `raw-init-endpoint-req` for only required fields
- `raw-init-endpoint-all` for all the fields
- `raw-init-site-yaml` for all the fields

### RQL validation
RQL validation happens after running the related yaml file. The errors will be visualized in the problem section as well as underlined inside the file.

### Running Yaml files

#### Endpoints without arguments
After setting up the top level site-yaml file as well as the child endpoint yaml files, in order to run the yaml files, navigate to RAW panel tab, and then click on the **Play Button** that is visible when hovering the yaml file. An alternative way to run the file is again navigate to RAW panel tab, then open the file in editor, **right click** in the text area and select `RAW - Run File` or press F8.

![Run Yaml](https://github.com/raw-labs/vscode/tree/main/imagesrun-yaml.png)

#### Endpoints with arguments
In order to run yaml files with arguments, click on `Add Argument Set` button on the left side of the editor. Then add any arguments needed for the invocation. Select the checkbox of the argument set that you want to use and then follow the steps described in [Endpoints without arguments](#endpoints-without-arguments). You can have multiple Argument Sets and select a different set per call.

![Run Yaml With Arguments](https://github.com/raw-labs/vscode/tree/main/imagesarguments.png)

### Listing Data Sources and Test Access
When authenticated the extension will automatically fetch the available Data Sources and visualize them at the bottom of RAW explorer. In order to Test Access to Data Sources, click on the Data Source.

![Data Sources](https://github.com/raw-labs/vscode/tree/main/imagesdata-sources.png)

### Scratchpad
From version 0.0.5 and on the extension supports scratchpad functionality. You still have to set up your git repository in order to use it.

#### Opening
In order to open scratchpad go to RAW extension panel tab -> RAW explorer -> RAW - Open Scratchpad

![Open Scratchpad](https://github.com/raw-labs/vscode/tree/main/imagesscratchpad-open.png)


For more advanced VS Code users there is also a command by pressing `ctl + shift + p` and type open scratchpad.

![Open Scratchpad With Command](https://github.com/raw-labs/vscode/tree/main/imagesscratchpad-with-command.png)

#### Running Code
In order to run the code there are 3 ways.
1. Right click -> RAW - Run Scratchpad Code
2. `F8` when focused on the scratchpad

![Right Click Run Click](https://github.com/raw-labs/vscode/tree/main/imagesscratchpad-right-click.png)

3. By pressing the Play button  when focused on the scratchpad

![Play Button](https://github.com/raw-labs/vscode/tree/main/imagesscratchpad-play.png)

## Extension Settings
**Please ignore this topic if you don't use multiple environments**

### Environment Setting
The default set environment is production (when the setting is empty), if you want to run the code against other environment, please change it in File -> Preferences -> Settings by searching RAW setting.

![Environment Settings](https://github.com/raw-labs/vscode/tree/main/imagesenv-setting.png)
  

## Known Issues

- Token has to be provided every 24 hours.
- No Grammar Semantics support for RQL.
- No basic file-system operations in RAW explorer, new files have to be created in VS Code basic explorer and then refresh on RAW Explorer.
- No way to provide new Data Sources, they have to be provided in RAW UI
- No support for embedded code into YAML file yet  

## Release Notes

For more details visit the changelog file

### 0.0.5
Added the scratchpad functionality

### 0.0.3
Initial internal release