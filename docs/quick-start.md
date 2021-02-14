# Getting started

## Prerequisites

* [GitHub](https://github.com/) / [GitLab](https://gitlab.com/) account
* [Netlify](https://app.netlify.com/) account

## Quick deployment

Thanks to Netlify, creating you own instance of Static Form is a one-click:

[![Deploy](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/zulvkr/StaticForm&stack=cms)

This button will tell Netlify to make a copy of **Static Form** in your GitHub, build the website in their edge server and set up the CI/CD automatically.

Now, you need to do some configuration to use the admin interface.

## Initial configuration

If you used deploy button, you should already receive invitation on your email to create user.

Click the link on the email, you will be directed to your new website and asked to create a password.

![signup](_media/complete-your-signup.png)

After finishing your sign up, go to admin page. Now, you should be able to login with your new account.

If you don't find the email invitation or not using deploy button, you should check/do the following configuration:

1. [Check if the git-gateway is enabled.](https://docs.netlify.com/visitor-access/git-gateway/)
2. [Check if you have enable Identity](https://docs.netlify.com/visitor-access/identity/)
3. [Check if you have been invited in Identity](https://docs.netlify.com/visitor-access/identity/registration-login/#invitations)
4. Check config.yaml use correct branch

## Next Steps

See **User Guide** section for detailed instruction how to use and costumize Static Form. For local development, see [Local Installation](local-installation.md)
