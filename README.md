# Shell Windows

A collection of tools for windows, window manager configuration, and information about active windows.

### record-window-titles

To automatically start the recording when logging in, put the launcher into the autostart group:

    $ cp ~/Unixhome/bin/ingo/shell-windows/config/record-window-titles.desktop ~/.config/autostart/

### full-window-title-report

This is intended to be installed as an (ana)cron job to run daily. When using for myself, I can just symlink it:

    $ sudo ln -s ~/Unixhome/bin/ingo/shell-windows/config/email-window-title-report /etc/cron.daily/email-window-title-report

The script will relaunch itself (`REPORTER_USER`) when it is started under the superuser.

To customize the reporting, create a wrapper file `/etc/cron.daily/email-window-title-report-somebody` instead.

- The user for which the reporting is done is specified as `REPORTEE_USER`; the user who runs the report needs to have read access to that user's reports.
- The (comma-separated) recipient(s) of the report are specified by `REPORT_EMAIL`.

    #!/bin/sh
    REPORTEE_USER=somebody REPORT_EMAIL=somebody@example.com exec ~/Unixhome/bin/ingo/shell-windows/config/email-window-title-report

- A different `REPORTER_USER` can do the reporting; however, that user then needs to have my Unixhome installed in their home directory.
