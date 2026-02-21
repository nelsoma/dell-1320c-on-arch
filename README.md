# Dell 1320c on Arch.
Notes on how to get a Dell 1320c laser colour printer working printer working on Arch.

## Packages
This includes a desktop config.
```bash
pacman -S cups system-config-printer cups-pk-helper print-manager ghostscript
```

32bit version of libcups, in Arch comes from `multilib` which might need to be enabled.
```bash
pacman -S lib32-libcups
```

Make sure cups is started.
```bash
sysctemctl enable cups && \
systemctl start cups
```

## Filters, ppd, etc.
Copy the contents of `/usr` to their respective places. Preserve permissions, and make sure to update ownership.

## Conifg
Log into the webgui at `http://localhost:631/admin` and add the printer, assuming its on usb.