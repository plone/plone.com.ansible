# ansible-role-supervisor

A role for creating supervisor tasks.


## Actions

- Ensures that supervisor is installed (using `apt`)
- Creates a task in the supervisor conf directory.


## Usage:
```
  roles:
    - role: nicholsn.supervisor
      name: webserver
      command: python -m SimpleHTTPServer
      directory: /opt/web
      startsecs: 2
      user: ubuntu
```

## License

MIT
