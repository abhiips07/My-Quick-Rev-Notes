shell: bourne shell
Bash: bourne again shell (enhanced version of shell)

---------------------------
## Essential Commands:
- `cd`: Change directory.
- `ls`: List directory contents.
- `pwd`: Print working directory.
- `mkdir`: Make directory.
- `rm`: Remove files or directories.
- `cp`: Copy files or directories.
- `mv`: Move or rename files or directories.
- `touch`: Create an empty file.
- `cat`: Concatenate and display files.
- `grep`: Search text patterns.
- `chmod`: Change file permissions.
- `chown`: Change file owner and group.
## System Management:
- `top`: Display Linux processes.
- `ps`: Show currently running processes.
- `kill`: Terminate processes.
- `sudo`: Execute a command as another user.
- `df`: Display disk space usage.
- `du`: Estimate file space usage.
- `free`: Display amount of free and used memory.
- `reboot`: Reboot the system.
- `shutdown`: Shutdown the system.
- `hostname`: Print or set system name.
- `ifconfig` (or `ip`): Configure network interfaces.
- `ping`: Test network connectivity.
## Package Management:
- `apt-get` (or `apt`): Package manager for Debian-based systems.
- `yum`: Package manager for Red Hat-based systems.
- `pip`: Package installer for Python.
- `npm`: Package manager for Node.js.
- `composer`: Dependency manager for PHP.
## Version Control:
- `git`: Distributed version control system.
- `svn`: Subversion version control system.
## Automation and Scripting:
- `cron`: Job scheduler.
- ***bash scripts***: Writing and executing bash scripts for automation.
## Networking:
- `ssh`: Secure shell for remote access.
- `scp`: Securely copy files between hosts.
- `rsync`: Remote file synchronization.
- `wget`: Retrieve files from the web.
## Monitoring and Logging:
- `tail`: Output the last part of files.
- `grep`: Search text patterns in files.
- `sed`: Stream editor for filtering and transforming text.
## Text Processing:
- `awk`: Text processing tool.
- `cut`: Remove sections from each line of files.
- `sort`: Sort lines of text files.
- `uniq`: Report or omit repeated lines.
- `tr`: Translate or delete characters.
## Docker and Containers:
- `docker`: Containerization platform.
- `docker-compose`: Define and run multi-container Docker applications.
## Deployment and Configuration Management:
- `ansible`: Configuration management and deployment tool.
- `chef`: Infrastructure automation framework.
- `puppet`: Configuration management tool.
- `terraform`: Infrastructure as code tool.
## Continuous Integration/Continuous Deployment (CI/CD):
- `jenkins`: Automation server for CI/CD pipelines.
- `gitlab-ci`: CI/CD integrated with GitLab.
- `travis-ci`: CI service for GitHub projects.
- `circle-ci`: CI/CD platform for continuous integration and delivery.
## Cloud Computing:
- `aws-cli`: AWS Command Line Interface.
- `gcloud`: Google Cloud SDK.
- `az-cli`: Azure Command-Line Interface.
## Logging and Monitoring:
- `prometheus`: Monitoring and alerting toolkit.
- `grafana`: Metrics dashboard and graph editor.
- `elasticsearch`: Distributed search and analytics engine.
- `kibana`: Data visualization dashboard for Elasticsearch.
## Security:
- `nmap`: Network exploration tool and security scanner.
- `fail2ban`: Intrusion prevention software.
## Miscellaneous:
- `curl`: Transfer data from or to a server.
- `tmux`: Terminal multiplexer.
- `jq`: Command-line JSON processor.
----------------------

# Important points
- shebang: #!/bin/bash
- if a variable is passed like this `ENV_VAR=value executable param1 param2` then it is defined for the period of that command execution only.
- when we defined a env variable using `export` then it is pass to all sub or child process called from that environment

# Variables
```bash
AGE=25
echo $AGE

readonly AGE		# marks the variable as readonly
unset AGE

func() {
	local AGE=25		# local variable (by default variables are global)
}
```

| Variable Type    | Syntax              | Description                                          |
|------------------|---------------------|------------------------------------------------------|
| Array            | declare -a variable | declare an indexedarray variable that stores strings |
| Associated Array | declare -A variable | Associated Array (key value pair)                                     |
| Integer          | declare -i variable | numeric value to store in variable                   |
| Readonly         | declare -r variable | readonly variable, cannot be changed or unset        |
| Export           | declare -x variable | export the variable and used by all child process    |


`printenv` or `env` for getting environment variables. Variables are case sensitive

# Comments
```bash
# single line

:'
multiline1
multiline2
'
```

# Array
```bash
array=(one two three)
array[0]=first index
array[-1]=last index
array[key1]=one		# for associated type

# for loop on array
nums=(1 3 12)
for i in "${nums[@]}"
do
  echo "$i"
done

${array[@]}		Get All elements
${array[*]}		Get All elements
${!array[!]}	Get All indexes
${#array[!]}	Array length
```

# if elif else
```bash
if condition1; then
	# true code
elif condition2; then
	# condition1 is false and condition2 is true
else
	# none of above condition are true
fi
```

- `[condition]` : file string operation
- `[[condition]]` : combining multiple conditions and handling regex pattern
- `((condition))` : for arithmatic operation

> - conditon is an expression that evaluates to `true` or `false`
> - Space is required before and after `[` and `]`
> - A semicolon before then is required

# Loops
## for
```bash
for element in [list]
# ex for element in 1 2 3 4 5
do
	echo $element
done

# index loop
for (( assignment; condition; iteration )); do
	# code block
done

for ((i=0; i<5; i++)); do
	echo $i
done
```

## while
```bash
while [ condition ]; do
	# code block
done

i=0
while [[ i -lt 100 ]]; do
	echo "$i"
	i=$((i+1))
done
```

##
