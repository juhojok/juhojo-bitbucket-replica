# Replicate a repository

You can find the public replica at [https://github.com/juhojok/juhojo-bitbucket-replica][1].

## Repository configuration

1. Create an empty repository in Bitbucket and GitHub
2. Create a GitHub [access token][2] (for personal accounts) or use a [machine user][3] (for organizations)
    - Copy the access token value into a file on your local machine
3. [Create SSH keys for the private Bitbucket repository and add the public key to repository's access keys*][4]
4. Configure the pipeline environment variables
    - `$BITBUCKET_URL` (public), can be SSH or HTTP
    - `$GITHUB_REPOSITORY_NAME` (public), just the repository name not the URL
    - `$GITHUB_USERNAME` (public), repository owner account name
    - `$GITHUB_TOKEN` (private), the access token you copied (step 2.)

> \* Since we are cloning the same repository I am pretty sure this step is extra

If your configuration is correct, the `bitbucket-pipelines.yml` should trigger on every commit and push your changes to the replica repository.

[1]: https://github.com/juhojok/juhojo-bitbucket-replica
[2]: https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token
[3]: https://docs.github.com/en/developers/overview/managing-deploy-keys#machine-users
[4]: https://bitbucket.org/blog/cloning-another-bitbucket-repository-in-bitbucket-pipelines
