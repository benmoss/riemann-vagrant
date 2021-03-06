[Riemann](http://aphyr.github.com/riemann/) is a very interesting
event agregation and monitoring tool. This repository aims to make
experimenting with it easier.

It does that by using two other lovely tools, namely
[Vagrant](http://vagrantup.com) and [Puppet](http://puppetlabs.com/).
You'll need to install Vagrant yourself but puppet comes included on the
specified box.

[![Build
Status](https://secure.travis-ci.org/garethr/riemann-vagrant.png)](http://travis-ci.org/garethr/riemann-vagrant)
[![Dependency
Status](https://gemnasium.com/garethr/riemann-vagrant.png)](http://gemnasium.com/garethr/riemann-vagrant)

## Usage

First you'll need to download the relevant Puppet modules, which are
managed via [Librarian
Puppet](https://github.com/rodjek/librarian-puppet).

    bundle install
    bundle exec librarian-puppet install

Once you have Vagrant installed choose which distro you prefer,
currently the module (and this repo) support centos and ubuntu. Run
either:

    vagrant up ubuntu

Or:

    vagrant up centos

Note that you can only run one of these at the same time (at least
without messing with the config) due to port forwarding being used.

This should download an Ubuntu or Centos base box and then use Puppet to install
Reinmann. It also installs the dashboard as an example, starts a
couple of daemons to start putting information into Riemann and also
uses the [Puppet report
processor](https://github.com/jamtur01/puppet-riemann) to load even more
data.

You can access the dashboard at http://localhost:4567 due to that port
being forwarded and if you're experimenting with the a Riemann client
you can access that on localhost:5555.

## License

Copyright (c) 2012 Gareth Rushgrove

Permission is hereby granted, free of charge, to any person obtaining a
copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be included
in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS
OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
