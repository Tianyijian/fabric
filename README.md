<div align="center">

<img src="./images/fabric-logo-gif.gif" alt="fabriclogo" width="400" height="400"/>

# `fabric-test-branch`

<p class="align center">
<h4><code>fabric</code> is an open-source framework for augmenting humans using AI.</h4>
</p>

</div>


## Introduction
Based on the main branch of the fabric, this test branch incorporates the following two features:

1. Use fabric with the [GLM](https://open.bigmodel.cn/) API KEY, which is almost entirely compatible with the OpenAI API.
2. Use [Rich](https://github.com/Textualize/rich) to enhance the markdown output in the terminal.

## Quickstart


1. Navigate to where you keep the Fabric project

```bash
# Find a home for Fabric
cd /where/you/keep/code
```

2. Clone the project to your computer.

```bash
# Clone Fabric to your computer
git clone https://github.com/Tianyijian/fabric.git
```

3. Enter Fabric's main directory.

```bash
# Enter the project folder (where you cloned it)
cd fabric
```

4. Switch to the test branch

```bash
# Switch to the test branch
git checkout test_branch
```

5. Install pipx:

macOS:

```bash
brew install pipx
```

Linux:

```bash
sudo apt install pipx
```

Windows:

Use WSL and follow the Linux instructions.

5. Install fabric:

```bash
pipx install .
```

6. Run setup:

```bash
fabric --setup
```

7. Modify the environment configuration file:

```bash
# Open and edit the .env file
vim ~/config/fabric/.env

OPENAI_API_KEY=GLM_API_KEY_HERE
OPENAI_BASE_URL=https://open.bigmodel.cn/api/paas/v4/
DEFAULT_MODEL=glm-4-0520
# Available models can be listed by command `fabric --listmodels`. glm-4-0520 and glm-4-airx are recommended.
``` 
8. Restart your shell to reload everything.

9.  Now you are up and running! You can test by running the help.

```bash
# Making sure the paths are set up correctly
fabric --help
```

## How to Use
### Rich

[Rich](https://github.com/Textualize/rich) is used by default in the normal `--text -t` output.
```bash
compare_and_contrast -t "bash, zsh"
``` 
You can choose not to use Rich in the `--stream -s` output or by adding `--no_rich -nr` to the normal output.
```bash
compare_and_contrast -s -t "bash, zsh"
compare_and_contrast -nr -t "bash, zsh"
``` 
### Examples
1. Run the `explain_code` Pattern based on input from `stdin`. In this case, the body of a snippet of code.

```bash
pbpaste | explain_code
```
2. Run the `summarize` Pattern based on the transcript of a Youtube video.
```bash
yt -t https://www.youtube.com/watch\?v\=OrxmtDw4pVI | summarize
``` 

## Updating

To update Fabric, run the following commands.

```bash
# From the fabric directory
pipx install . --force
fabric --update
```