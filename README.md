**PLEASE NOTE: These instructions are for Exercism Admins only. Maintainers should request that admins create a new representer for them. Please create a new topic on the [forum](https://forum.exercism.org).**

---

# Exercism Representer Template

This repository is a [template repository](https://help.github.com/en/github/creating-cloning-and-archiving-repositories/creating-a-template-repository) for creating [representers][representers] for [Exercism][exercism] tracks.

To create a new representer, use the `bin/bootstrap.sh` script:

```shell
LANGUAGE=Ruby SLUG=ruby bin/bootstrap.sh
```

This will automatically:

1. Create the representer repository
1. Setup access for the `maintainers-admin` team and the track-specific team
1. Setup branch protection rules
1. Give this repository access to the secrets required to deploy the image
1. Disable merge and rebase commits

## Deployment

Once the representer is ready to be tested/deployed, you need to:

- Manually push the image to Docker hub
  - Give the `bots` team "read/write" permissions to the newly pushed image
- Create a pull request to the [exercism/terraform][terraform] repository
  - Once merged, provision the latest version to the servers
- Manually trigger the `deploy` workflow

[terraform]: https://github.com/exercism/terraform/
