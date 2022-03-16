<h1 align="center">
  <br>
  <a href="http://eka.to"><img src="https://raw.githubusercontent.com/Lotus-King-Research/Home/main/Assets/Images/Lotus-King-Research-Logo-Transparent.png" alt="Lotus King Research" width="200"></a>
  <br>
</h1>

<h3 align="center">Transifex Worfklow Template</h3>

<p align="center">
  
  <a href="https://mirrors.creativecommons.org/presskit/buttons/88x31/png/by-sa.png">
    <img width=150px src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/12/Cc-by-nc-sa_icon.svg/1280px-Cc-by-nc-sa_icon.svg.png" alt="License">
  </a>
</p>

<p align="center">
  <a href="#description">Description</a> •
  <a href="#docs">Docs</a>
</p>
<hr>

## Description

A template repository for setting up Transifex translation workflow. Replace the content in this section with the title of your project.

## Docs

### 1) Add the source text

Start by adding the source text to [root/](root) directory of this repository. 

**NOTE:** The source text should be segmented in the way where each line in the file represents a fragment of text to be translated (i.e. loosely speaking a sentence).

### ) Create the translation resources 

Create a new branch in Github named `first_phase` by clicking the branches selector, then typing `first_phase` into the text and clicking `Create branch`. This will automatically prepare everything for Transifex


### ) Create a new project in Transifex

Go to `Dashboard` from the top navigation menu and click `Create new project` button from the bottom of the screen.

Give a name to your project, and choose `File based: Upload a language file (eg. po, yml, xliff) with your contents` under the `Choose project type` heading. Set `Source language` and `Target language` and then click `Create project`. 

**NOTE:** The directory names in [wip/](wip) directory have to correspond with the source and target language codes in Transifex. The default is `bo` and `en`. 

### ) Making the connection between Github and Transifex

Start by clicking the project name on the left navigation pane, and then choosing `Settings`.

From `Settings` choose `Integrations` tab.

```
filters:
  - filter_type: file
    file_format: PO
    source_language: en
    source_file: wip/bo/001.po
    translation_files_expression: 'wip/<lang>/001.po'
```