# YFMARCO Recovery Builder |TWRP / PBRP / OFRP / SHRP|
Compile your first custom recovery via Github Actions - with ldcheck setup.

> ⚙️ **This repo now runs on a `self-hosted` runner.** The GitHub-hosted runners are no longer used. You must add your own runner before running any workflow.

## Self-hosted runner setup
1. Go to **Settings → Actions → Runners → New self-hosted runner**.
2. Choose **Linux / x64** and run the given commands on your machine (download, extract, and `./config.sh`).
3. Start it with `./run.sh` (or install it as a service).
4. Make sure your runner has:
   - `sudo` access for the runner user (passwordless `sudo` recommended).
   - At least **20–40 GB free disk** (recovery sync + build), 8+ GB RAM, and a 64-bit OS.
   - Internet access (to download packages, the Android repo, and Node for actions).
5. Add the repository secrets (see below).

## How to Use
1. Fork this repository.

## How to build in case of private repository
1. Create a token.
2. Enter the repository settings.
3. Go to the Secrets and variables option then to Actions.
4. Create a new repository secret.
5. The first thing you will name "RECOVERY_TOKEN" is where you will put the Token.
6. The second secret is called "RECOVERY_USERNAME" This is where you will enter the email address associated with your GitHub account.

2. Go to `Action` tab > `All workflows` > Pick which Build you need (`TWRP or PBRP or OFRP or SHRP`) > `Run workflow`, then pick required information from each drop-down list:
 - Manifest Branch (*14.1,*12.1, *11.0, *10.0, *9.0, *8.1, *7.1, *6.0, etc.)
 - Device Tree (Your device tree repository link)
 - Device Tree Branch (Your device tree repository branch)
 - Build Target (boot, reecovery, vendorboot)
 - LDCHECK (path to your target binary file, ie. `system/bin/qseecomd`)
   - If you are building manually/locally and you want to use ldcheck for checking dependencies, visit [THIS](https://github.com/TeamWin/android_device_qcom_twrp-common/tree/android-11#using-ldcheck-to-find-dependencies) this for guide.

> ⚠️ **Security note:** Workflows run arbitrary code on your own machine. The builds are locked to the repo owner only (`owner.id == sender.id`), but never add public/unknown contributors to the repository while a self-hosted runner is attached.

## Thanks/Credits
 - [YFMARCO-Dev](https://github.com/YFMARCO-Dev)
 - [CaptainThrowback](https://github.com/CaptainThrowback)
 - [azwhikaru](https://github.com/azwhikaru)
 - [cd-Crypton](https://github.com/cd-Crypton)
 - [that1](https://github.com/that1)
 - [carlodandan](https://github.com/carlodandan)
 - [lazycodebuilder](https://github.com/lazycodebuilder)
 - And to all Contributors in every repositories and scripts I used.