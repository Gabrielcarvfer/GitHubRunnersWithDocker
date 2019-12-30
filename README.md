GitHub runners with Docker (with Hyper-V isolation)
===========================

Start by cloning the repo, then create a `.env` file with the following:

```
GITHUB_REPO_URL=https://github.com/your_use_name/your_repo
GITHUB_REPO_TOKEN_WINDOWS=token_generated_for_windows_in_https://github.com/your_use_name/your_repo/settings/actions
GITHUB_REPO_TOKEN_LINUX=token_generated_for_linux_in_https://github.com/your_use_name/your_repo/settings/actions
```

You will probably need to manually update the runners and Git for Windows installers URLs with the most up to date.

To build the docker images, run:
```
docker-compose up (-d to run as deamon)
```

To start the runners, run:
```
docker-compose start
```

Now you should be able to send workloads to your runner.

To stop the runners:
```
docker-compose stop
```

To remove the docker-compose registry, networking stuff and containers:
```
docker-compose down
```

To remove older images:
```
docker image rm github_runner_docker_githubrunnerwindows
docker image rm github_runner_docker_githubrunnerlinux
```
More info about self-hosted runners can be found in: https://help.github.com/pt/actions/automating-your-workflow-with-github-actions/adding-self-hosted-runners
