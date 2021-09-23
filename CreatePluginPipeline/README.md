# Build Kaholo Plugin - Template Pipeline
This pipeline creates a repo and a directory for it on the agent.
Than creates all the reuired files for a kaholo plugin, generated from a plugin configuration file provided to it.

![Build Kaholo Plugin Pipeline Image](https://github.com/kaholo/kaholo-template-pipelines/blob/main/pipelineImage.png?raw=true)

## Requirments
In order to have this pipeline working you need to have:
* Kaholo Server in Version 3.2.2 or higher.
* Kaholo agent in version 2.0.0 or higher installed on a computer you have access to(preferably not from a virtual machine).
* The following plugins installed:
* **[Kaholo Plugin - Git](https://github.com/Kaholo/Kaholo-plugin-git)** version 2.3.2 or higher.
* **[Kaholo Plugin - Github](https://github.com/Kaholo/Kaholo-plugin-github)** version 1.2.3 or higher.
* **[Kaholo Plugin - Text Editor](https://github.com/Kaholo/Kaholo-plugin-textEditor)** version 1.1.0 or higher.
* **[Kaholo Plugin - File System](https://github.com/Kaholo/Kaholo-plugin-fs)** version 2.1.0 or higher.
* **[Kaholo Plugin - Command Line](https://github.com/Kaholo/Kaholo-plugin-cmd)** version 2.0.1 or higher.

## Setting Up The Pipeline
Take the following steps to configure the pipeline:
1. Download the Resources.zip file in this repo to the agent you'll be running this pipeline on. The files inside are required for the pipeline to run later on this agent.
2. Create a new directory on that agent, and unpack the zip in there.
3. Create a new directory for the plugins that will be created on this agent. Default name is "plugins", but it can be anything. If choosing a different name for this directory, edit the variable 'pluginsPath' in the pipeline's code accordingly.
4. Download the file BuildKaholoPlugin.js from this repo. This file contains
5. Go to Kaholo and choose the Projects tab, and than choose the project to create the new pipeline in.
6. Choose 'Import pipeline' and than choose the pipeline doenloaded before(BuildKaholoPlugin.js).
7. Update the authentication data for the git plugin and for the github plugin, either in the plugin settings or inside the methods in the pipeline.
8. Update The variable named 'mainPath' in the code segment of the pipeline. Insert the path of the directory created in step 2 as the value for this variable.

## Executing the pipeline
In order to run the pipeline and generate files for new kaholo plugins, you need to create two things first:
1. Create a Kaholo plugin configuration for the new plugin and make sure you have it stored on the agent running this pipeline.
2. Create a configuration file for this pipeline in the "Configurations" tab of the pipeline, according to this format:
```json
{
    "org": "Insert Owner Name For The New Github Repository ",
    "description": "Kaholo plugin for...",
    "configPath": "Insert path to the configuration file of the new plugin",
    "makeHelpers": true,
    "includeParsers": true
}
```
* Make sure to choose the new configuration before executing the pipeline.
