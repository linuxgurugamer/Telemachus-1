Telemachus Supporting Project | Readme
=
[![Build status](https://flat.badgen.net/appveyor/ci/DanGSun/Telemachus-1)](https://ci.appveyor.com/project/DanGSun/telemachus-1)
[![](https://flat.badgen.net/github/stars/TeleIO/Telemachus-1)](https://github.com/TeleIO/Telemachus-1/stargazers)
[![](https://flat.badgen.net/github/assets-dl/TeleIO/Telemachus-1)]()
[![Discord Chat](https://img.shields.io/discord/695052938095231016.svg)](https://discord.gg/3f7JNH)

#### Discord
https://discord.gg/3f7JNH

Current status of project:
* New Part System
* Changed UI
* Integrated Houston + Mkon
* Automated Building Pipeline

#### External Connection Note
This mod includes version checking using [MiniAVC](http://forum.kerbalspaceprogram.com/threads/79745). If you opt-in, it will use the internet to check whether there is a new version available. Data is only read from the internet and no personal information is sent. For a more comprehensive version checking experience, please download the [KSP-AVC plugin](http://forum.kerbalspaceprogram.com/threads/79745).


#### Building (&testing) telemachus-reborn
* this differs from the old original build docu found here:[Building](https://github.com/richardbunt/Telemachus/wiki/Building)

* clone the git repo
* install visual studio (e.g. 2017 or 2015)+ ".net desktop environment"(at least needed on visual studio 2017)
* open the solution in visual studio: `$YOURGITREPO/Telemachus.sln`
* in visual studio: choose between a debug or a release build:
  * Build->Configuration Manager
  * in top left select Debug or Release, whatever you like (in a Debug build all `PluginLogger.debug("..foobar")` debug-print-statements will show up in KSP.log/debug console, in a release build they won't)
* click Build->Build Solution and wait
* the actual telemachus build artefacts will be copied to `$YOURGITREPO/Telemachus/bin/Debug` / `$YOURGITREPO/Telemachus/bin/Release`  by visual studio
* The AfterBuild.(bat/sh) script will copy together all kinds of files(build artefacts+external deps (MKON,houston), telemachus DLLs + parts etc) into `$YOURGITREPO/publish`.
  * Make sure to provide the project directory (the directory `AfterBuild.sh` lives in and the target directory (e.g. `bin/debug`) as the first and second argument, respectively (e.g. `./AfterBuild.sh . bin/debug` if running from the directory `AfterBuild.sh` lives in).
  * for mkon&houston: mkon & houston releases are simply downloaded from github,extracted and copied into the right place under `$YOURGITREPO/publish/GameData/Telemachus/Plugins/PluginData/Telemachus/...` 

* to test a build copy the complete folder `Telemachus` found under `$YOURGITREPO/publish/GameData/` into your KSP install under `$KSPinstall/GameData/` and start ksp. you maybe want to delete a preexisting `Telemachus` folder in your `$KSPinstall/GameData`.
* start a game, go to the VAB, use a mk1-pod
* under command-control select 1 of the 2 telemachus antennas, put them on your vessel & fly/launch
* right click on the telemachus-antenna and select 'open link' - your browser should open a webpage served by your telemachus-mod (e.g. http://127.0.0.1:8085/ )

