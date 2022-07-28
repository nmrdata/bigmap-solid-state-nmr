# Solid state NMR dataset

This folder shows an example of a dataset that can be published on GitHub and is readable directly from NMRium.

The principle is quite easy, you create folder containing jcamp files (extension `dx` or `jdx`) and optionally a molfile (extension `.mol`).

If you have [node](https://nodejs.org/en/) installed it is super easy to generate the correct json toc allowing to visualize the data from the web.

```bash
npm i --global nmrium-cli
nmrium createGeneralTOC
```

You can then publish the project on 'gh-pages' and it will be accessible directly from the browser.

https://www.nmrium.org/nmrium#?toc=https%3A%2F%2Fnmrdata.github.io%2Fsolid%2Ftoc.json
