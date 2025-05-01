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
