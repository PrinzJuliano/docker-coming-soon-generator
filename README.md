# Docker coming-soon Generator

Serves a "comming soon" page for you filled with content from your environment variables.

I took the [bootstrap4 comming soon](BlackrockDigital/startbootstrap-coming-soon) template as default
and wrote a docker deploy script with twig template compiler where you can pick and run a page within minutes.

Here is an example of the result:

![bootstrap4-example](templates/bootstrap4/example.png)

# Usage
Please set environment variable `TEMPLATE` to pick one of these avaliable templates.
If you don't pick a template, `bootstrap4` is default

| Template | Preview |
| -------- | ------- |
| bootstrap4 | <img src="templates/bootstrap4/example.png" width="250"> |

You have the following environment variables which allow you to configure the
coming soon page:



| Variable name | Description                            | used in Templates | Example                                                                |
|-----------------|------------------------------------------- | -------------------- | ---------------------------------------------------------------------------------|
| TITLE         | Webpage head title and heading              | bootstrap4 | Coming Soon!                                                   |
| SUBLINE       | The sentence under the title                | bootstrap4 | We're working hard to finish the development of this site. Our target launch date is <strong>January 2019</strong>!                |
| FACEBOOK_URL  | Facebook URL to your page      | bootstrap4 | https://www.facebook.com/yourPage                     |
| TWITTER_URL   | Twitter URL to your page       | bootstrap4 | https://www.twitter.com/yourPage                       |
| GITHUB_URL    | Github URL to your page        | bootstrap4 | https://www.github.com/yourPage                         |

## what happen at Build ?
1. Checkout missing templates with `checkout.sh` script into `templates`
2. move template (name stored in env) `TEMPLATE` to root
3. remove templates folder with unused templates
4. write config file from env if file missing
5. compile `index.html.twig` into `index.html` with config.json as variables


## Contributing

If you're able to add more templates or optimise anything you're welcome.
New templates? Just check out or add them into `templates` folder, create `index.html.twig` file
and keep records of used environment variables in `README.md


## kudos
by the way there is another comming soon for docker
[zedtux/docker-coming-soon](zedtux/docker-coming-soon) - may this is working better for you?