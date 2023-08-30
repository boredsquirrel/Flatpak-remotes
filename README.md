# Flatpak-remotes
A list of public Flatpak repositories. Feel free to add missing ones!

# Stable repositories

## [Flathub](https://flathub.org)

    flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
  
## [Fedora Flatpaks](https://fedoraproject.org/wiki/SIGs/Flatpak#Why_do_we_need_Fedora_Flatpaks?)

    flatpak remote-add --if-not-exists fedora https://registry.fedoraproject.org
    
## [ElementaryOS](https://appcenter.elementary.io/)

    flatpak remote-add --if-not-exists elementaryos https://flatpak.elementary.io/repo.flatpakrepo


## [EndlessOS](http://endlessm.github.io/eos-knowledge-lib/contributing)
Key expired 2021!

    flatpak remote-add --if-not-exists --from eos-sdk http://endlessm.github.io/eos-knowledge-lib/eos-sdk.flatpakrepo
    
    
## [PureOS](https://puri.sm/posts/introducing-flatpaks-on-pureos/)

    flatpak remote-add --if-not-exists PureOS https://store.puri.sm/repo/stable/pureos.flatpakrepo

## [Igalia](https://software.igalia.com/)
for [Gobby](https://gobby.github.io/), [Linphone](https://gobby.github.io/) and [Revolt](https://github.com/aperezdc/revolt/) (unmaintained)

    flatpak remote-add --if-not-exists igalia https://software.igalia.com/flatpak-refs/igalia.flatpakrepo

# unstable Repositories

## [Flathub Beta](https://discourse.flathub.org/t/how-to-use-flathub-beta/2111)

    flatpak remote-add --if-not-exists flathub-beta https://flathub.org/beta-repo/flathub-beta.flatpakrepo

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
