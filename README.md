# Flatpak-remotes
A list of public Flatpak repositories. Feel free to add missing ones!

Use the `--user` flag to install them for this user only and remove the `flatpak` group / root privilege dependency. This will break some apps that rely on elevated privileges for hardware access, like [GPU Screen Recorder](https://flathub.org/apps/com.dec05eba.gpu_screen_recorder), in exchange for an abstract security benefit.

When installing as system repo, use `usermod -aG flatpak $USER` or an equivalent command, to avoid needing to be in the `wheel` group.

# Stable repositories

## [Flathub](https://flathub.org)

    flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo

Flathub also has subsets, allowing you to exclude apps with certain antifeatures.

#### Verified
Only Apps supported by upstream (official) Developers end up here. Quite a few are missing

    flatpak remote-add --if-not-exists --subset=verified flathub-verified https://dl.flathub.org/repo/flathub.flatpakrepo

#### FLOSS
Only Open Source Apps end up here. This should calm down Richard Stallman

    flatpak remote-add --if-not-exists --subset=floss flathub-floss https://dl.flathub.org/repo/flathub.flatpakrepo  

#### FLOSS & Verified
Least apps, highest trustworthiness

    flatpak remote-add --if-not-exists --subset=verified_floss flathub-verified_floss https://dl.flathub.org/repo/flathub.flatpakrepo

Note for changing from a subset to all:

The `--subset=` argument is currently incomplete as [there is no `subset=all`](https://github.com/flatpak/flatpak/issues/5637). Workarounds:
- `flatpak remote-modify --subset= flathub` (will leave behind `xa.subset-is-set=true`)
- `flatpak remote-delete --force flathub && flatpak remote-add flathub https://dl.flathub.org/repo/flathub.flatpakrepo`


## [Fedora Flatpaks](https://fedoraproject.org/wiki/SIGs/Flatpak#Why_do_we_need_Fedora_Flatpaks?)
Apps built with Fedoras built system and own runtime. Up to date, pretty secure, mostly not officially supported but packaged by Fedora Contributors. The list is also pretty small, so many people just remove it. It is the default on Fedora and will stay, legal reasons.

    flatpak remote-add --if-not-exists fedora https://registry.fedoraproject.org
    
## [ElementaryOS](https://appcenter.elementary.io/)

    flatpak remote-add --if-not-exists elementaryos https://flatpak.elementary.io/repo.flatpakrepo
    
## [PureOS](https://puri.sm/posts/introducing-flatpaks-on-pureos/)
Often outdated, but "more secure" apps, from the Purism developers.

    flatpak remote-add --if-not-exists PureOS https://store.puri.sm/repo/stable/pureos.flatpakrepo

## [Igalia](https://software.igalia.com/)
For [Gobby](https://gobby.github.io/), [Linphone](https://gobby.github.io/), the Webkit SDK and [Revolt](https://github.com/aperezdc/revolt/) (unmaintained)

    flatpak remote-add --if-not-exists igalia https://software.igalia.com/flatpak-refs/igalia.flatpakrepo

# Unstable Repositories

## [Flathub Beta](https://discourse.flathub.org/t/how-to-use-flathub-beta/2111)

    flatpak remote-add --user --if-not-exists flathub-beta https://flathub.org/beta-repo/flathub-beta.flatpakrepo

subsets should work here too

If apps have the same name, run them like this: `flatpak run --branch=beta org.gimp.GIMP`

## EndlessOS Nightly

    flatpak remote-add --user --if-not-exists --from eos-sdk http://endlessm.github.io/eos-knowledge-lib/eos-sdk.flatpakrepo

## [KDE Nightly](https://userbase.kde.org/Tutorials/Flatpak#Nightly_KDE_apps)
The single repo is discontinued, now every nightly app has its own. You will always need the nightly runtime.

    flatpak remote-add --user --if-not-exists kde-runtime-nightly https://cdn.kde.org/flatpak/kde-runtime-nightly/kde-runtime-nightly.flatpakrepo

Example for dragon-nightly:

    flatpak remote-add --user --if-not-exists dragon-nightly https://cdn.kde.org/flatpak/dragon-nightly/dragon-nightly.flatpakrepo
    flatpak install dragon-nightly dragonplayer

You can find all of them [here](https://cdn.kde.org/flatpak). 

### KDE XWayland Videobridge Nightly
Compatibility bridge to make screensharing for legacy apps work on Wayland, now as a Flatpak.

    flatpak remote-add --user xwaylandvideobridge-nightly https://cdn.kde.org/flatpak/xwaylandvideobridge-nightly/xwaylandvideobridge-nightly.flatpakrepo

## [GNOME Nightly](https://wiki.gnome.org/Apps/Nightly)
Also contains GIMP nightly (whereas GIMP beta is on Flathub-beta)

    flatpak remote-add --user --if-not-exists gnome-nightly https://nightly.gnome.org/gnome-nightly.flatpakrepo
    
## [Eclipse Nightly](http://eclipse.matbooth.co.uk/flatpak/nightlies.html)
(Flathub needed for dependencies)

    flatpak remote-add --user --if-not-exists eclipse-nightly https://download.eclipse.org/linuxtools/flatpak-I-builds/eclipse.flatpakrepo

## WebKit SDK for Epiphany Canary
(together with GNOME Nightly)

    flatpak remote-add --user --if-not-exists webkit-sdk https://software.igalia.com/flatpak-refs/webkit-sdk.flatpakrepo

## Firefox & Thunderbird

### [Firefox Nightly](https://gitlab.com/projects261/firefox-nightly-flatpak)

    flatpak install --user https://gitlab.com/projects261/firefox-nightly-flatpak/-/raw/main/firefox-nightly.flatpakref
    
### [Thunderbird Nightly](https://gitlab.com/projects261/thunderbird-nightly-flatpak)
Flatpak build from the nightly/daily release binary. This command adds the remote.

    flatpak install --user https://gitlab.com/projects261/thunderbird-nightly-flatpak/-/raw/main/thunderbird-nightly.flatpakref

### [Firefox ESR](https://gitlab.com/projects261/firefox-esr-flatpak)

    flatpak install --user https://gitlab.com/projects261/firefox-esr-flatpak/-/raw/main/firefox-esr.flatpakref

### [Firefox Dev Edition](https://gitlab.com/projects261/firefox-dev-flatpak)

    flatpak install --user https://gitlab.com/projects261/firefox-dev-flatpak/-/raw/main/firefox-dev.flatpakref

## Other Projects
[Davinci Resolve Flatpak](https://github.com/pobthebuilder/resolve-flatpak) allows packaging it locally.


# Warnings

## ~~[EndlessOS](http://endlessm.github.io/eos-knowledge-lib/contributing)~~
Key expired 2021!

    #flatpak remote-add --if-not-exists --from eos-sdk #http://endlessm.github.io/eos-knowledge-lib/eos-sdk.flatpakrepo
    

## ~~[WinePak](https://winepak.github.io/)~~
[Website seems to have been hijacked, DONT USE](https://github.com/winepak/winepak/issues/27), project is unmaintained for 6 years.

    #flatpak remote-add --if-not-exists winepak #https://dl.winepak.org/repo/winepak.flatpakrepo
