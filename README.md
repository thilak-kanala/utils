# Development Utils

A collection of utility scripts.

## Unity Git LFS Setup Script

### `setup-unity-git-lfs.sh`

Automatically configures Git LFS for Unity projects with proper file tracking and ignore patterns.

#### Features

- 🚀 **Automated Setup**: One-command setup for Git LFS in Unity projects
- 📁 **Comprehensive File Tracking**: Tracks all common Unity asset types (3D models, textures, audio, video, etc.)
- 🛡️ **Safe Execution**: Creates backups of existing configuration files
- 🎨 **Colored Output**: Clear, colored terminal output for better user experience
- ✅ **Validation**: Checks for Git repository and Unity project structure
- 📋 **Complete .gitignore**: Includes comprehensive Unity .gitignore patterns plus macOS system files

#### Usage

**Basic Usage:**
```bash
# Setup Git LFS in current directory (if it's a Unity project)
./setup-unity-git-lfs.sh

# Setup Git LFS in a specific Unity project directory
./setup-unity-git-lfs.sh /path/to/unity/project

# Examples
./setup-unity-git-lfs.sh ~/Documents/MyUnityGame
```

**Get Help:**
```bash
./setup-unity-git-lfs.sh --help
```

The script accepts an optional path argument to the Unity project directory. If no path is provided, it will attempt to set up Git LFS in the current directory.

#### What it does

1. **Validates Environment**:
   - Checks if you're in a Git repository
   - Verifies Unity project structure
   - Ensures Git LFS is installed

2. **Configures Git LFS**:
   - Initializes Git LFS in the repository
   - Creates comprehensive `.gitattributes` with Unity-specific patterns
   - Updates `.gitignore` with Unity-specific rules and macOS system files

3. **File Tracking**: Automatically tracks these file types with Git LFS:
   - **3D Models**: `.fbx`, `.obj`, `.blend`, `.max`, `.ma`, `.mb`, etc.
   - **Audio**: `.wav`, `.mp3`, `.ogg`, `.aiff`, etc.
   - **Images**: `.png`, `.jpg`, `.psd`, `.tga`, `.exr`, etc.
   - **Video**: `.mp4`, `.mov`, `.avi`, `.wmv`, etc.
   - **Unity Assets**: `.unity`, `.asset`, `.cubemap`, `.unitypackage`
   - **Archives**: `.zip`, `.rar`, `.7z`, etc.
   - **Executables**: `.dll`, `.exe`, `.apk`, etc.

#### Requirements

- Git installed and repository initialized in the target directory
- Git LFS installed (`brew install git-lfs` on macOS)
- Unity project structure (Assets/ and ProjectSettings/ folders) in target directory

#### Example Output

```
================================
 Unity Git LFS Setup Script
================================

[INFO] Using Unity project directory: /Users/username/MyUnityProject
[INFO] Git repository detected in: /Users/username/MyUnityProject
[INFO] Unity project structure detected in: /Users/username/MyUnityProject
[INFO] Checking Git LFS installation...
[INFO] Git LFS is installed. Initializing...
[INFO] Creating .gitattributes file for Unity...
[INFO] Setting up .gitignore for Unity...
[INFO] Configuring Git LFS tracking...

✅ Unity Git LFS Setup Complete!

Project Directory: /Users/username/MyUnityProject

Summary of changes:
  ✓ Git LFS initialized
  ✓ .gitattributes created with Unity file patterns
  ✓ .gitignore updated with Unity rules and macOS system files

Next steps:
  1. Review the generated .gitattributes file
  2. Navigate to project: cd '/Users/username/MyUnityProject'
  3. Add and commit your files: git add . && git commit -m 'Initial Unity project setup with Git LFS'
  4. Push to remote: git push origin main
```

#### Safety Features

- Creates `.gitattributes.backup` and `.gitignore.backup` if files already exist
- Non-destructive - won't overwrite existing Git LFS configurations
- Validates environment before making changes
- Provides clear feedback on all operations

#### Troubleshooting

**"Not in a git repository"**
- Run `git init` in your Unity project root first, or provide the correct path to an initialized Git repository

**"Git LFS is not installed"**
- Install Git LFS: `brew install git-lfs` (macOS) or visit [git-lfs.github.io](https://git-lfs.github.io/)

**"Directory does not exist or is not accessible"**
- Check that the provided path exists and you have read/write permissions
- Use absolute paths or ensure relative paths are correct from your current location

**"This doesn't appear to be a Unity project"**
- Make sure the target directory contains Assets/ and ProjectSettings/ folders
- You can continue anyway if you want to set up Git LFS for a different type of project

---

## License

MIT License - Feel free to use and modify as needed.