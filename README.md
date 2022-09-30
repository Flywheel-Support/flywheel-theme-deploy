# Flywheel Theme Deploy Example

[![Flywheel SSH Deploy](https://github.com/matthewselby/fly-theme-deploy/actions/workflows/main.yml/badge.svg?branch=main)](https://github.com/matthewselby/fly-theme-deploy/actions/workflows/main.yml)

[Flywheel Help doc - Deploy to Flywheel via SSH and GitHub Actions](https://getflywheel.com/wordpress-support/deploying-to-flywheel-via-ssh-and-github-actions/)

This is an example of how to deploy a theme directory `awesome-theme` to your site's `/wp-content/themes` directory on hosted on Flywheel. It is currently set up to deploy to the Flywheel Site on every change commited to the Master or Main branch.

While you can deploy more than just one specific Theme or Plugin, it's recommended to keep your deploys scoped to aviod conflicts.

---

This deploy example requires two variables, `SSH_USER` and `PRIVATE_KEY` to be set in the repositories Actions Secrets.

`SSH_USER` is the unique SSH User listed when Direct SSHing into the site. This is listed on the Flywheel Site Dashboard > Advanced tab > Connect via SSH.

<img width="400" alt="Connect via SSH in Flywheel Dashboard" src="https://user-images.githubusercontent.com/14359078/193362754-440162ea-2e11-42cc-84ed-477747f379ac.png">

In this example, Connect via SSH has the code below displayed:

`ssh team+awesome-org+awesome-site@ssh.getflywheel.com`

and the SSH User is:

`team+awesome-org+awesome-site`

Create a new Action Secret under the Settings tab of the GitHub repository for `SSH_USER` with the username displayed for your site:

<img width="400" alt="SSH_USER Actions Secret" src="https://user-images.githubusercontent.com/14359078/193364020-cb0c4970-e42e-4960-857e-19df70809230.png">
<img width="400" alt="GitHub Actions Secrets" src="https://user-images.githubusercontent.com/14359078/193364037-758e1864-9a8a-45e6-aab9-411f056a2dee.png">


The second Actions Secret needed is for `PRIVATE_KEY`. This will be the Private Key conterpart to Public Key set in your Flywheel Account:

<img width="400" alt="Flywheel Account SSH Keys" src="https://user-images.githubusercontent.com/14359078/193363295-6fa863f3-d13a-4745-a81d-078270c93773.png">

More info at this link for [SSH Key Access and Management](https://getflywheel.com/wordpress-support/ssh-key-access-and-management/).
