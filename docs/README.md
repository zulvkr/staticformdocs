# Static Form 📝

**Static Form** is a form builder that built with JAMStack. The entire stack is JavaScript based and leveraging Netlify services to make it easy to get onboard. It is made to be static-with-JS-sprinkle kind of website which makes it lightning fast

No form backend is provided. Instead, **Static Form** uses various third party form endpoint.

## Features

* Form builder with instant preview.
* Super performant website (90+ lighthouse test).
* Extendable with themes and components.
* Easy deployment.

## Built using

* [Eleventy](https://www.11ty.dev/)
* [Netlify CMS](https://www.netlifycms.org/)
* [Tailwind CSS](https://tailwindcss.com/)
* [Alpine.js](https://github.com/alpinejs/alpine)

**[Netlify](https://www.netlify.com/)** provides the backend, which includes:

* Static edge hosting.
* Form API endpoint.
* Authentication server.

**Static Form** is configured to work with WhatsApp wa.me link and Netlify Form as form endpoint, and both has some [limitations](#). You can use any other form backend like Formspree ([there are lots of provider out there](https://free-for.dev/#/?id=forms)) or build your own.
