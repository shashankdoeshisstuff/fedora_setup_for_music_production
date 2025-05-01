# Fedora Music Production Setup

## Install wine

packages link =>  https://dl.winehq.org/wine-builds/fedora/

sudo dnf remove wine wine-core winehq-staging winehq-devel winehq-stable

dnf list --showduplicates winehq-staging

sudo dnf install ./wine-staging-8.10-*.rpm --allowerasing

sudo dnf install winehq-staging-8.10 --allowerasing

wine --version

wine-8.10

### Lock the version
sudo dnf versionlock add winehq-staging

### Remove the version lock
sudo dnf versionlock delete winehq-staging

## Manually add the repo in fedora

sudo nano /etc/yum.repos.d/winehq.repo

## Add this content
[WineHQ]
name=WineHQ packages
type=rpm-md
baseurl=https://dl.winehq.org/wine-builds/fedora/38
gpgcheck=1
gpgkey=https://dl.winehq.org/wine-builds/winehq.key
enabled=1

### Install with this command
sudo dnf install winehq-staging-8.20-1.2 --allowerasing


### Added this for low memory lock issue
@audio   -  rtprio     95
@audio   -  memlock    unlimited
@realtime - rtprio     95
@realtime - memlock    unlimited

### Disable rtkit daemon 
sudo systemctl disable --now rtkit-daemon


In file => /etc/security/limits.conf
