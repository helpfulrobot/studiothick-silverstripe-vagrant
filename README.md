# silverstripe-vagrant

## System requirements

On your development machine you will need:

 * [Virtualbox](https://www.virtualbox.org/)
 * [Vagrant](https://www.vagrantup.com/)
 * [Ansible](http://docs.ansible.com/intro_installation.html)
 * [vagrant-vbguest](https://github.com/dotless-de/vagrant-vbguest)

## Install

    composer require studiothick/silverstripe-vagrant --dev

## Launch

    $ cd vagrant
    $ vagrant up

For the first launch virtual box will throw an `VERR_PDM_DRIVER_NOT_FOUND` error.
This is related to the audio driver. Just open Virtualbox, select the new image,
under the Audio tab and untick the audio driver checkbox. After that

    $ vagrant up

Now another error appears because `vbguest` package is not installed. Just run

    $ vagrant vbguest

and then

    $ vagrant reload --provision
