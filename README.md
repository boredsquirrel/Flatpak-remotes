# Flatpak-remotes
A list of public Flatpak repositories. Feel free to add missing ones!

Use the `--user` flag to install them for this user only and remove the `flatpak` group / root privilege dependency. This will break some apps that rely on elevated privileges for hardware access, like [GPU Screen Recorder](https://flathub.org/apps/com.dec05eba.gpu_screen_recorder). When installing as system repo, use `usermod -aG flatpak $USER` or an equivalent command.

# Stable repositories

## [Flathub](https://flathub.org)

    flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo

Flathub also has subsets, allowing you to exclude apps with certain antifeatures.

#### Verified
Only Apps supported by upstream (official) Developers end up here. Quite a few are missing

    flatpak remote-add --if-not-exists --subset=verified flathub-verified https://flathub.org/repo/flathub.flatpakrepo

#### FLOSS
only Open Source Apps end up here. This should calm down Richard Stallman

    flatpak remote-add --if-not-exists --subset=floss flathub-floss https://flathub.org/repo/flathub.flatpakrepo  

#### FLOSS & Verified
least apps, highest trustworthiness

    flatpak remote-add --if-not-exists --subset=verified_floss flathub-verified_floss https://flathub.org/repo/flathub.flatpakrepo

the `flatpak remote-modify --subset=X` command is currently broken and [there is no `subset=all`](https://github.com/flatpak/flatpak/issues/5637) so this is not recommended.

If someone finds the link to the docs, please post it, I am again unable to find it.

## [Fedora Flatpaks](https://fedoraproject.org/wiki/SIGs/Flatpak#Why_do_we_need_Fedora_Flatpaks?)
Apps built with Fedoras built system and own runtime. Up to date, pretty secure, mostly not officially supported but packaged by Fedora Contributors. The list is also pretty small, so many people just remove it. It is the default on Fedora and will stay, legal reasons.

    flatpak remote-add --if-not-exists fedora https://registry.fedoraproject.org
    
## [ElementaryOS](https://appcenter.elementary.io/)

    flatpak remote-add --if-not-exists elementaryos https://flatpak.elementary.io/repo.flatpakrepo


## ~~[EndlessOS](http://endlessm.github.io/eos-knowledge-lib/contributing)~~
Key expired 2021!

    flatpak remote-add --if-not-exists --from eos-sdk http://endlessm.github.io/eos-knowledge-lib/eos-sdk.flatpakrepo
    
    
## [PureOS](https://puri.sm/posts/introducing-flatpaks-on-pureos/)

    flatpak remote-add --if-not-exists PureOS https://store.puri.sm/repo/stable/pureos.flatpakrepo

## [Igalia](https://software.igalia.com/)
for [Gobby](https://gobby.github.io/), [Linphone](https://gobby.github.io/), the Webkit SDK and [Revolt](https://github.com/aperezdc/revolt/) (unmaintained)

    flatpak remote-add --if-not-exists igalia https://software.igalia.com/flatpak-refs/igalia.flatpakrepo

# Unstable Repositories

## [Flathub Beta](https://discourse.flathub.org/t/how-to-use-flathub-beta/2111)

    flatpak remote-add --if-not-exists flathub-beta https://flathub.org/beta-repo/flathub-beta.flatpakrepo

subsets should work here too

## EndlessOS Nightly

    flatpak remote-add --if-not-exists --from eos-sdk http://endlessm.github.io/eos-knowledge-lib/eos-sdk.flatpakrepo

 ## [KDE Nightly](https://apps.kde.org/)

    flatpak remote-add --if-not-exists kdeapps https://distribute.kde.org/kdeapps.flatpakrepo
    
## [GNOME Nightly](https://wiki.gnome.org/Apps/Nightly)

    flatpak remote-add --if-not-exists gnome-nightly https://nightly.gnome.org/gnome-nightly.flatpakrepo
    
## [Eclipse Nightly](http://eclipse.matbooth.co.uk/flatpak/nightlies.html)
(Flathub needed for dependencies)

    flatpak remote-add --if-not-exists eclipse-nightly https://download.eclipse.org/linuxtools/flatpak-I-builds/eclipse.flatpakrepo

## WebKit SDK for Epiphany Canary (GNOME Nightly)
(together with GNOME Nightly)

    flatpak remote-add --if-not-exists https://software.igalia.com/flatpak-refs/webkit-sdk.flatpakrepo
