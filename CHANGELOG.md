# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## Unreleased

### Added

### Changed

### Deprecated

### Removed

### Fixed

### Security

## 0.4.0

Released on January 20th, 2026.

### Added

- `delete_files_flow` - New flow for deleting files from remote servers based on pattern matching and filtering. Works with LOCAL, SFTP, and RCLONE connection types.
- `delete_file_task` - New task for deleting a single file from a remote server.
- `delete_asset` - New helper function that provides core deletion logic shared across tasks.
- `password_utils` - New utility module with `get_password_value()` helper for properly handling Pydantic SecretStr password fields.

### Fixed

- **CRITICAL**: Fixed SecretStr password handling in all tasks (`list_remote_files_task`, `download_file_task`, `upload_file_task`, `delete_file_task`). Previously, when using `ServerWithBasicAuthBlock` with SFTP connections, passwords were passed as SecretStr objects instead of being unwrapped, causing `TypeError: Expected unicode or bytes, got <class 'pydantic.types.SecretStr'>`.
- Refactored `download_asset` to use the new shared `delete_asset` helper for move operations, improving code maintainability.

## 0.1.0

Released on ????? ?th, 20??.

### Added

- `task_name` task - [#1](https://github.com/ImperialCollegeLondon/prefect-managedfiletransfer/pull/1)
