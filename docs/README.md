# Static Form 📝

**Static Form** is a form builder that built with JAMStack. The stack is JavaScript based and leveraging Netlify services to make it easy to get on board. It is made to be static-with-JS-sprinkle kind of website which makes it lightning fast

No form back end is provided. Instead, **Static Form** uses various third party form endpoint.

## Features

* Form builder with instant preview.
* Super performance website (90+ lighthouse test).
* Extensible with themes and components.
* Easy deployment.

## Built using

* [Eleventy](https://www.11ty.dev/)
* [Netlify CMS](https://www.netlifycms.org/)
* [Tailwind CSS](https://tailwindcss.com/)
* [Alpine.js](https://github.com/alpinejs/alpine)

**[Netlify](https://www.netlify.com/)** and GitHub / GitLab provides the back end, which includes:

* Hosting.
* Form API endpoint.
* Authentication server.

**Static Form** is configured to work with WhatsApp wa.me link and Netlify Form as form endpoint, and both has some [limitations](#). You can use any other form back end like Formspree ([there are lots of provider out there](https://css-tricks.com/a-comparison-of-static-form-providers/)) or build your own.
