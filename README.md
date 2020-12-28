# Shell Windows

A collection of tools for windows, window manager configuration, and information about active windows.

### record-window-titles

To automatically start the recording when logging in, put the launcher into the autostart group:

    $ setup-record-window-titles

### full-window-title-report

You can use this to get an overview about what you've done today so far, or to cover larger timespans of the past. But this is mostly used for the automatically generated email reports.

### email-window-title-report

This is intended to be installed as an (ana)cron job to run daily. When using it for myself, I can just symlink it:

    $ sudo ln -s {~/bin/ingo/shell-windows/etc/email-window-title-report,/etc/cron.daily}/email-window-title-report-job

(The script will relaunch itself as myself when it is started under the superuser by cron.)

#### configuration

Reporting needs at least the recipient email address. You can use one of the example configurations in the [config/email-window-title-report/](config/email-window-title-report/) subdirectory, or create your own; [config/email-window-title-report/template.conf](config/email-window-title-report/template.conf) documents all possible values.
This must be copied into `~/.config/email-window-title-report/*.conf`; each shell script there is sourced and triggers one report.
