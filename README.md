# appimage2deb

`appimage2deb` is a bash script that converts AppImage files to Debian packages (.deb). This tool allows you to manage AppImage applications using the Debian package manager, making it easier to install, update, and remove these applications on Debian-based systems.

## Features

- Converts AppImage files to Debian packages
- Integrates AppImage applications into the system (desktop entries, icons)
- Automates the packaging process for multiple systems
- Preserves application metadata

## Why Use appimage2deb?

1. **Centralized Management**: Manage all applications with the Debian package manager.
2. **Security**: Enables scanning of applications not directly from Debian repositories.
3. **Automation**: Simplifies the process of converting AppImages for multiple systems.

## Dependencies

Before using this script, ensure you have the following packages installed:

```
sudo apt install libappimage-dev wget squashfs-tools dpkg-dev
```

## Usage

```
./appimage2deb -a <appimage_path> -m <maintainer> -d <description>
```

### Options:

- `-a`: Path to the AppImage file (required)
- `-m`: Maintainer information (required)
- `-d`: Description of the application (required)

### Example:

```
./appimage2deb -a /path/to/your/app.AppImage -m "John Doe <john@example.com>" -d "A fantastic application"
```

## Output

The script will create a Debian package (.deb) in the `builds` directory within the script's location. The package name will follow the format:

```
<app_name>_<version>_<architecture>.deb
```

## How It Works

1. Extracts the AppImage
2. Gathers metadata from the AppImage
3. Creates necessary Debian package structure
4. Generates control file and maintainer scripts
5. Integrates application with desktop environment (icons, .desktop file)
6. Builds the Debian package

## TODO

- Remove the need for command-line options and use variables from `.bashrc`
- Add scanning of contents for malware, trackers, and vulnerabilities
- Create Software Bill of Materials (SBOM)
- Implement semantic versioning for sansnom
- Sign packages with sansnom GPG key

## Author

Martin Stadler (martin@sansnom.co.uk)

## License

MIT

## Contributing

Submit a PR

## Support

If you encounter any problems or have any questions, please open an issue on this GitHub repository.
