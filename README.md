# Shell Windows

A collection of tools for windows, window manager configuration, and information about active windows.

### record-window-titles

To automatically start the recording when logging in, put the launcher into the autostart group:

    $ cp ~/Unixhome/bin/ingo/shell-windows/config/record-window-titles.desktop ~/.config/autostart/

### full-window-title-report

This is intended to be installed as a (ana)cron job to run daily. When using for myself, I can just symlink it:

    $ sudo -H ln -s ~/Unixhome/bin/ingo/shell-windows/config/email-window-title-report /etc/cron.daily/email-window-title-report

When using it for / sending to somebody else, create a wrapper file `/etc/cron.daily/email-window-title-report-somebody` instead:

    #!/bin/sh
    REPORT_USER=somebody REPORT_EMAIL=somebody@example.com exec ~/Unixhome/bin/ingo/shell-windows/config/email-window-title-report
