# Add self-hosted runner

Adding a self-hosted runner requires that you download, configure, and execute the GitHub Actions Runner. By downloading and configuring the Github Actions Runner, you agree to the GitHub Terms of Service or GitHub Corporate Terms of Service, as applicable.

## Download

We recommend configuring the runner under `C:\actions-runner`. This will help avoid issues related to service identity folder permissions and long path restrictions on Windows.

__NOTE:__ Run commands below as Administrator.

```
# Create a folder under the drive root
$ mkdir actions-runner; cd actions-runner
# Download the latest runner package
$ Invoke-WebRequest -Uri https://github.com/actions/runner/releases/download/v2.278.0/actions-runner-win-x64-2.278.0.zip -OutFile actions-runner-win-x64-2.278.0.zip
# Extract the installer
$ Add-Type -AssemblyName System.IO.Compression.FileSystem ; [System.IO.Compression.ZipFile]::ExtractToDirectory("$PWD/actions-runner-win-x64-2.278.0.zip", "$PWD")
```

```
# Open Services using shortcut __Windows + R__ then on run dialog type *services.msc* locate __GitHub Actions Runner__ open proprierties tem go to Logon tab and select __Local System account__ click OK and restart de service.

## Configure

```
# Create the runner and start the configuration experience
$ ./config.cmd --url https://github.com/n0lr4m/mkdocs-self-hosted-runners --token APFMFHICIFA7IF7LSL53FITARYNM4
# Run it!
$ ./run.cmd
```

## Using your self-hosted runner

```
# Use this YAML in your workflow file for each job
runs-on: self-hosted
```



