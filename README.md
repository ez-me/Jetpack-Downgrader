# Jetpack Downgrader | [Download](https://github.com/Zalexanninev15/Jetpack-Downgrader/releases/latest) | [Topic](https://gtaforums.com/topic/969056-jetpack-downgrader)

![alt](https://github.com/Zalexanninev15/Jetpack-Downgrader/raw/main/logo.png)

<p>
<a href="https://github.com/Zalexanninev15/Jetpack-Downgrader/releases" target="_blank">
      <img alt="All releases" src="https://img.shields.io/github/downloads/Zalexanninev15/Jetpack-Downgrader/total.svg?style=for-the-badge&logo=github" />
    </a>    
<a href="https://github.com/Zalexanninev15/Jetpack-Downgrader/releases/latest" target="_blank">
      <img alt="Latest release" src="https://img.shields.io/github/downloads/Zalexanninev15/Jetpack-Downgrader/latest/total.svg?style=for-the-badge&logo=github" />
    </a>    
</p>
<p>
<a href="https://github.com/Zalexanninev15/Jetpack-Downgrader/stargazers" target="_blank">
      <img alt="GitHub stars" src="https://img.shields.io/github/stars/Zalexanninev15/Jetpack-Downgrader.svg?style=for-the-badge&logo=github" />
<a href="https://github.com/Zalexanninev15/Jetpack-Downgrader/blob/master/LICENSE">
      <img alt="License" src="https://img.shields.io/github/license/Zalexanninev15/Jetpack-Downgrader.svg?style=for-the-badge&logo=github" />
</a>
</p>

## Description

App for downgrading the game Grand Theft Auto: San Andreas to version 1.0. 
Is required .NET Framework 4.8 and Windows 7/8/8.1/10

## Authors

* Zalexanninev15 - programmer and creator (Donate on [QIWI](https://qiwi.com/n/ZALEXANNINEV15) or [YooMoney](https://yoomoney.ru/to/410015106319420))
* Vadim M. - consultant ([Donate on Patreon](https://www.patreon.com/NationalPepper))

## Features

* As simple as possible interaction (default). Specify the folder and answer the questions - you can easily get version 1.0 with the necessary parameters
* The ability to fine-tune the downgrading process, the Jetpack Downgrader itself, and some other aspects
* Using delta patches that weigh significantly less than the files from the game version 1.0
* Smart checking for different versions and other aspects that will help you perform downgrades, in many cases, successfully
* Easy integration of the application as a separate component in your project
* Display of downgred process and maximum speed of operation

## Supported versions

* 1.0 [exe only] (if **Forced=true**)
* 1.01 [exe only] 
* 2.0 [fully supported]
* Steam [fully supported]
* Rockstar Games Launcher [fully supported]

**Only licensed versions of the game are supported, work on pirated builds is not guaranteed and will never be added!!!**

## Usage and configuration

1. Run **jpd.exe** and select the folder with the game (if **SelectFolder=true**)
2. Answer the questions (if **UseMsg=true**) and wait for the end of the work...
### Settings in jpd.ini

##### !!!THE SETTINGS ARE CHANGED BEFORE LAUNCHING THE APP!!!

In **jpd.ini**, you can specify the settings for this application, it is not recommended to change anything if you don't know exactly what each setting is responsible for and what its values and results are!!!


#### [Downgrader]

* **CreateBackups** - creating backups (full file name + .bak) of files before downgrading them
* **CreateShortcut** - creating a shortcut to a file **gta_sa.exe** on the desktop (only after a successful downgrade)
* **ResetGame** - deleting the game configuration file - **gta_sa.set** (after getting the game version)
 * **RGLGarbage** - remove unnecessary files (**index.bin** and **MTLX.dll**) from the Rockstar Games Launcher version of the game (after getting the game version). These files are not used in the game version 1.0
* **RegisterGamePath** - add entries to the registry so that the game is better recognized by mods and programs (e.g.: launchers, SAMP and other projects) (only after a successful downgrade)
* **CreateNewGamePath** - make a copy of the game folder (folder name + _Downgraded) to prevent accidental updates to the game (after MD5-scan). It is highly recommended to enable it for the Steam/Rockstar Games Launcher versions of the game!!!
* **Forced** - force the app to continue running even if EXE file are already use from the game version 1.0 (MD5). Downgrader will only work with the EXE file, the rest of the game files will just be checked, so they must be original. For non-1.0 versions, only the EXE file will be patched

#### [JPD]

* **SelectFolder** - using UI for select the folder with the game (path using **Copmonent=true**, overwritten to a new one)
* **ConsoleTransparency** - use transparency for the console
* **UseMsg** - use Windows message boxes to notify you when you select an action, as well as to show a positive result of the application's performance. This setting can take values instead of (or have no effect on) the settings: **CreateBackups**, **CreateShortcut**, **ResetGame**, **RGLGarbage**, **RegisterGamePath**,  **CreateNewGamePath** and **Forced** 
* **UseProgressBar** - use the progress bar to indicate the progress of each of the downgrader stages. During operation, all logs of the current stage of work are ignored!!!
* **Component** - this setting is **only** necessary if you decide to use *Jetpack Downgrader* in your projects (this setting will help you skip the UI (in console) and removes the waiting for input after the processes in the app are completed). This setting adds the ability to specify the path to the game folder as a parameter for launching the application

 Example for CMD: 

  ```shell
jpd "E:\Games\Grand Theft Auto San Andreas"
  ```

#### [Only]

* **GameVersion** - get only the game version (can be used with the settings **ResetGame** and/or **RGLGarbage**)
* **NextCheckFiles** - get only the game version and check files (only those that are used for downgrading)
* **NextCheckFilesAndCheckMD5** - the same as **NextCheckFiles**, but it also scan files by MD5 and reveals which files are used from the game version 1.0 (information will only be visible if **UseProgressBar=false**)

## Build

Compile using Visual Studio 2019
