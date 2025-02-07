# EC3 - Elastic compute cloud companion

This script allows you to manage your AWS EC2 instances using keywords defined in a mapping file. You can start, stop, list, and check the status of instances.

## Installation

Please follow the installation steps in [INSTALL.md](./INSTALL.md) to set up the script.

## Usage

```bash
ec3 <start|stop|list|status> [keyword]
```

- `start`: Start the instance associated with the keyword.
- `stop`: Stop the instance associated with the keyword.
- `list`: List all instances defined in the mapping file.
- `status`: Check the status of the instance associated with the keyword.

## Mapping File

The mapping file (`~/.ec3rc`) should contain lines in the following format:

```
<keyword>=<instance_id>:<region>
```

Example:

```
webserver=i-1234567890abcdef:us-west-2
database=i-0987654321fedcba:us-east-1
```

## Example

To start an instance:

```bash
ec3 start webserver
```

To stop an instance:

```bash
ec3 stop webserver
```

To list all instances:

```bash
ec3 list
```

To check the status of an instance:

```bash
ec3 status webserver
```