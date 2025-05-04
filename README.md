# File Management System


A complete file management system implemented in C that simulates a basic operating system file structure with directory management, file operations, and user authentication.

## Features

- 🔒 **Password Authentication** - Secure root login with password protection
- 📁 **Directory Operations** - Create, delete, and navigate directories
- 📄 **File Management** - Create, delete, read, and write files
- 🕒 **Metadata Tracking** - File creation dates, sizes, and attributes
- 💾 **Persistent Storage** - Virtual disk that saves between sessions
- 🖥️ **Interactive Shell** - Command-line interface for system interaction

## Technology Stack

- **Core**: C Programming Language
- **Data Structures**: Custom FAT (File Allocation Table) implementation
- **Security**: Password input masking
- **Persistence**: Virtual disk saved to physical file

## Installation

### Prerequisites

- GCC compiler
- Linux/Unix environment (for terminal compatibility)
- Make utility (optional)

### Compilation

```
gcc -o filesystem main.c
```

### Running the System

```
./filesystem
```

Default root password: `rootpassword`

## Commands

| Command | Parameters | Description |
|---------|------------|-------------|
| `cd`    | directory  | Change current directory |
| `mkdir` | name       | Create new directory |
| `rmdir` | name       | Remove directory |
| `ls`    | -          | List directory contents |
| `create`| filename   | Create new file |
| `rm`    | filename   | Remove file |
| `open`  | filename   | Open a file |
| `write` | -          | Write to opened file |
| `read`  | -          | Read opened file |
| `close` | -          | Close opened file |
| `-h`    | -          | Show help menu |
| `exit`  | -          | Exit the system |

## File System Structure

```
Virtual Disk Layout:
- Block 0: Boot block (system info)
- Blocks 1-2: FAT1 (File Allocation Table)
- Blocks 3-4: FAT2 (FAT backup)
- Blocks 5+: Data area (files and directories)
```

## Technical Details

- **Block Size**: 1024 bytes
- **Total Blocks**: 1000 (~1MB storage)
- **Max Filename**: 8 characters + 3 character extension
- **File Attributes**: Read-only, Hidden, System, Volume Label, Directory, Archive

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/NewFeature`)
3. Commit your changes (`git commit -m 'Add some feature'`)
4. Push to the branch (`git push origin feature/NewFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Inspired by traditional FAT filesystems
- Uses standard C libraries for portability
- Time/date handling based on DOS conventions

----

**Note**: This is an educational project. For production use, consider adding:
- Stronger password hashing
- File permission systems
- Larger disk capacity
- Journaling for crash recovery
