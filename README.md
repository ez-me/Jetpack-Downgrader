# Jetpack Downgrader | [Latest release](https://github.com/Zalexanninev15/Jetpack-Downgrader/releases/latest) | [Topic](https://gtaforums.com/topic/969056-jetpack-downgrader)

![alt](https://github.com/Zalexanninev15/Jetpack-Downgrader/raw/dev/data/logo.png)

[![](https://img.shields.io/badge/OS-Windows-informational?logo=windows)](https://github.com/Zalexanninev15/Jetpack-Downgrader)
[![](https://img.shields.io/github/v/release/Zalexanninev15/Jetpack-Downgrader)](https://github.com/Zalexanninev15/Jetpack-Downgrader/releases/latest)
[![](https://img.shields.io/github/downloads/Zalexanninev15/Jetpack-Downgrader/total.svg)](https://github.com/Zalexanninev15/Jetpack-Downgrader/releases)
[![](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

## Description

App for downgrading the game Grand Theft Auto: San Andreas to version 1.0. 
Is required .NET Framework 4.8 and Windows 7/8/8.1/10

## Authors

* Zalexanninev15 - programmer and creator [![](https://img.shields.io/badge/donate-QIWI-FF8C00.svg)](https://qiwi.com/n/ZALEXANNINEV15) [![](https://img.shields.io/badge/donate-YooMoney-8B3FFD.svg)](https://yoomoney.ru/to/410015106319420)
* Vadim M. - consultant [![](https://img.shields.io/badge/donate-Patreon-FF424D.svg)](https://www.patreon.com/NationalPepper)

## Features

* As simple as possible interaction (default). Specify the folder and answer the questions - you can easily get version 1.0 with the necessary settings
* The ability to fine-tune the downgrading process, the *Jetpack Downgrader* itself, and some other aspects
* Using delta patches that weigh significantly less than the files from the game version 1.0
* Smart checking for different versions and other aspects that will help you perform downgrades, in many cases, successfully
* Easy integration of the application as a separate component in your project
* Display process of downgrade and maximum speed of operations

## Supported versions

* 1.0 [exe only] (if **Forced=true**)
* 1.01 [exe only] 
* 2.0 [fully supported]
* Steam [fully supported]
* Rockstar Games Launcher [fully supported]

**Only licensed versions of the game are supported, work on pirated builds is not guaranteed and will never be added!!!**

## Usage and configuration

1. Run **jpd.exe** and select the folder with the game (if **SelectFolder=true**)
2. Answer the questions (if **UseMsg=true**) and wait end of work...

### Settings in jpd.ini

In **jpd.ini**, you can specify the settings for this application, it is not recommended to change anything if you don't know exactly what each setting is responsible for and what its values and results are!!! It is important to remember that settings are always more important than the answer you have chosen (if **UseMsg=true**)

#### [Downgrader]

* **CreateBackups** - creating backups (**[full file name] + .bak**) of original files before downgrading them
* **CreateShortcut** - creating a shortcut to a file **gta_sa.exe** on the desktop (only after a successful downgrade)
* **ResetGame** - remove the game configuration file **gta_sa.set** for prevents crash (after getting game version)
* **GarbageCleaning** - remove unneeded files (**index.bin** and **MTLX.dll**) from the Rockstar Games Launcher version of the game (after getting game version). These files are not used in the game version 1.0
* **RegisterGamePath** - add entries to the registry so that the game is better recognized by mods and programs (e.g.: launchers, SAMP and other projects) (only after a successful downgrade)
* **CreateNewGamePath** - make a copy of the game folder (**[folder name] + _Downgraded**) to prevent accidental updates to the game (after MD5-scan). It is highly recommended to enable it for the Steam/Rockstar Games Launcher versions of the game!!!
* **Forced** - force the app to continue running even if EXE file are already use from the game version 1.0 (MD5). Downgrader will only work with the EXE file, the rest of the game files will just be checked, so they must be original. For non-1.0 versions, only the EXE file will be patched
* **EnableDirectPlay** - enable the Windows DirectPlay component to run the game on Windows 10 (after getting game version)
* **InstallDirectX** - install additional DirectX files to run the game (after getting game version)

#### [JPD]

* **SelectFolder** - using UI for select the folder with the game (path using **Copmonent=true**, overwritten to a new one)
* **ConsoleTransparency** - use transparency for console
* **UseMsg** - use Windows message boxes to notify you when you select an action, as well as to show a positive result of the application's performance. This setting can take values instead of (or have no effect on) the settings: **CreateBackups**, **CreateShortcut**, **ResetGame**, **GarbageCleaning**, **RegisterGamePath**, **CreateNewGamePath**, **Forced**, **EnableDirectPlay**, **InstallDirectX** 
* **UseProgressBar** - use the progress bar to indicate the progress of each of the downgrader stages. During operation, all logs of the current stage of work are ignored!!!
* **Component** - this setting is **only** necessary if you decide to use *Jetpack Downgrader* in your projects (this setting will help you skip the UI (in console) and removes the waiting for input after the processes in the app are completed). This setting adds the ability to specify the path to the game folder as a parameter for launching the application

 Example for CMD: 

  ```shell
jpd "E:\Games\Grand Theft Auto San Andreas"
  ```

#### [Only]

* **GameVersion** - get only the game version (can be used with the settings **ResetGame**, **GarbageCleaning**, **EnableDirectPlay**, **InstallDirectX**)
* **NextCheckFiles** - get only the game version and check files (only those that are used for downgrading)
* **NextCheckFilesAndCheckMD5** - the same as **NextCheckFiles**, but it also scan files by MD5 and reveals which files are used from the game version 1.0 (information will only be visible if **UseProgressBar=false**)

## Build

Open solution *Jetpack Downgrader* and compile project *Downgrader* using Visual Studio 2019
