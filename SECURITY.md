# Security Policy

## Overview

This document outlines security best practices for this repository to prevent accidental exposure of sensitive information.

## Personal Information Protection

### What to Avoid

1. **Personal Identifiers**
   - Do not commit files containing full names, email addresses, or phone numbers
   - Avoid using personal usernames in configuration files
   - Remove location-specific information from code and configurations

2. **Local System Paths**
   - Avoid absolute paths that reveal system usernames or directory structures
   - Use relative paths or environment variables instead
   - Example: Use `arm-none-eabi-gcc` instead of `C:/Users/YourName/tools/arm-none-eabi-gcc.exe`

3. **Credentials and Secrets**
   - Never commit API keys, passwords, or authentication tokens
   - Use environment variables for sensitive configuration
   - Utilize secrets management tools for production deployments

### Git History

**Note:** Git commit history contains author information (name and email) that cannot be removed without rewriting history (which requires force pushing and can break existing clones).

To protect your identity in future commits:
```bash
# Configure Git with privacy-conscious settings
git config user.name "YourPseudonym"
git config user.email "noreply@example.com"
```

## IDE Configuration

### VSCode Settings

The `.vscode` directory contains configuration files that may include personal information:

- **c_cpp_properties.json**: Should use generic compiler paths
- **launch.json**: Should use relative paths only
- **tasks.json**: Should not contain user-specific commands

Personal VSCode settings should be added to `.vscode/settings.json` which is ignored by git.

## Reporting Security Issues

If you discover a security vulnerability or accidentally committed sensitive information:

1. **For sensitive commits**: Contact the repository owner immediately
2. **For vulnerabilities**: Open an issue with details (without exposing the vulnerability publicly)
3. **For urgent issues**: Use GitHub's private security advisory feature

## Best Practices Checklist

- [ ] Review all files before committing
- [ ] Use `.gitignore` to prevent accidental commits
- [ ] Use relative paths in configuration files
- [ ] Never commit credentials or API keys
- [ ] Configure Git with privacy-conscious name/email
- [ ] Review git diff before pushing changes
- [ ] Use environment variables for sensitive data
- [ ] Regularly audit repository for exposed information

## .gitignore

This repository includes a `.gitignore` file that excludes:
- Build artifacts
- Personal configuration files
- Environment files
- Temporary files
- IDE-specific settings (partial)

## Additional Resources

- [GitHub Security Best Practices](https://docs.github.com/en/code-security)
- [Removing sensitive data from a repository](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/removing-sensitive-data-from-a-repository)
- [Git Tools - Rewriting History](https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History)
