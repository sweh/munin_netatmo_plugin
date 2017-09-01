# munin_netatmo_plugin
Munin plugin that generates beautiful graphs from your netatmo weather stations

## Installation

This plugin is written in Python >= 2.7. It uses the `lnetatmo` library to connect to the netatmo
api. It is recommended to use `virtualenv` instead of installing `lnetatmo` into your system pythons
site packages.

    $ cd /path/to/munin_netatmo_plugin
    $ virtualenv --no-site-packages .
    $ bin/pip install lnetatmo

Setup your environment from Netatmo Web interface and save your credentials to
~/.netatmo.credentials file as described unter
https://github.com/philippelt/netatmo-api-python/blob/master/usage.md.

Once thats done you can link this plugin into the munin plugins folder:

    $ sudo ln -s netatmo_ /etc/munin/plugins/netatmo_Temperature
    $ sudo ln -s netatmo_ /etc/munin/plugins/netatmo_Humidity
    $ sudo ln -s netatmo_ /etc/munin/plugins/netatmo_CO2
    $ sudo ln -s netatmo_ /etc/munin/plugins/netatmo_Noise
    $ sudo ln -s netatmo_ /etc/munin/plugins/netatmo_Pressure
    $ sudo ln -s netatmo_ /etc/munin/plugins/netatmo_Rain
    $ sudo ln -s netatmo_ /etc/munin/plugins/netatmo_Wind

Additionally you must specify the user with the netatmo credentials in its home directory. Append

    [netatmo_*]
    user = sweh

to `/etc/munin/plugin-conf.d/munin-node`.

Now restart `munin-node` and take a look at the logs if everything is doing fine.
