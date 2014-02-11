# Debian package files for cutting edge Emacs

Here are the file customized from [Julien Danjou's Emacs-snapshot archive](http://emacs.naquadah.org/)

## How it works

    $ sudo apt-get build-dep emacs-snapshot
    $ sudo apt-get install dh_make 
    $ git clone https://github.com/GongYiLiao/EmacsSnapshotDebian.git
    $ git clone git://git.savannah.gnu.org/emacs.git
    $ cd emacs
	$ git pull
	$ cd ..
	$ cp -r emacs emacs-snapshot-[date]

where ```[date]``` is the first item in ```EmacsSnapshotDebian/changelog```

    $ cd emacs-snapshot-[date]
    $ cp -r ../EmacsSnapshotDebian ./debian
	$ dh_make --createorig
	$ dpkg-buildpackage -rfakeroot

It takes around 10 ~ 25 minutes, depends on your computing power. 
