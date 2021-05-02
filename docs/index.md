# Adding self-hosted runners

You can add a self-hosted runner to a repository, an organization, or an enterprise.


## Adding a self-hosted runner to a repository

You can add self-hosted runners to a single repository. To add a self-hosted runner to a user repository, you must be the repository owner. For an organization repository, you must be an organization owner or have admin access to the repository.

On GitHub Enterprise Server, navigate to the main page of the repository.

Under your repository name, click Settings.
In the left sidebar, click Actions.

Under "Self-hosted runners," click __Add runner__.


Select the operating system and architecture of your self-hosted runner machine.

You will see instructions showing you how to download the runner application and install it on your self-hosted runner machine.

Open a shell on your self-hosted runner machine and run each shell command in the order shown.


__Note:__ On Windows, if you want to install the self-hosted runner application as a service, you must open a shell with administrator privileges. We also recommend that you use `C:\actions-runner` as the directory for the self-hosted runner application so that Windows system accounts can access the runner directory.

The instructions walk you through completing these tasks:

* Downloading and extracting the self-hosted runner application.
* Running the config script to configure the self-hosted runner application and register it with GitHub Actions. The `config` script requires the destination URL and an automatically-generated time-limited token to authenticate the request.

* Running the self-hosted runner application to connect the machine to GitHub Actions.


#### Checking that your self-hosted runner was successfully added

After completing the steps to add a self-hosted runner, the runner and its status are now listed under "Self-hosted runners".

The self-hosted runner application must be active for the runner to accept jobs. When the runner application is connected to GitHub Enterprise Server and ready to receive jobs, you will see the following message on machine's terminal.

```
√ Connected to GitHub

2019-10-24 05:45:56Z: Listening for Jobs
```

