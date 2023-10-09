# Add startup apps on Ubuntu

## Open startup applications

```bash
gnome-session-properties
```

Add the `command` to the startup applications list. The `command` is the command that you would run in the terminal to start the application.

## find the command to run the app

Most default applications will have a `.desktop` file located in `/usr/share/applications`.
To find out about the corresponding terminal command that will be run when launching one of these applications open the file browser Nautilus and right click on the application's icon to select `Properties` in the context menu.
some example commands: Firefox(`firefox`), Spotify(`spotify`), Hyper(`hyper`), VS Code(`code`)

- Reference
  [Auto start apps and fix them to workspaces on startup — Ubuntu](https://medium.com/@mukherjeekalpan/auto-start-apps-and-fix-them-to-workspaces-on-startup-ubuntu-a1124f1af7f3#:~:text=So%20first%20off%20you%20need,the%20icon%20that%20shows%20up.&text=In%20the%20window%20that%20shows%20up%2C%20select%20Add.)