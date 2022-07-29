# Solid state NMR visualization

## Short summary

The goal of this project is to provide an open source microservice (app) for the visualization and analysis of solid-state NMR data accessible via a modern web front-end (React).

The project is open-source (MIT license) and is available on https://git.nmrium.org. An exhaustive documentation can be found on https://docs.nmrium.org.

In order to show the possibilities, we have created a solid state NMR dataset in this repository.
It can be previewed [here](https://www.nmrium.org/nmrium#?toc=https%3A%2F%2Fnmrdata.github.io%2Fsolid%2Ftoc.json).

## Integration in your own React website

## Creating your own databaset

This folder shows an example of a dataset Solid State NMR dataset that can be published on GitHub and visualize directly from [NMRium](https://www.nmrium.org/).

The principle is quite simple, you create folder containing jcamp files (extension `dx` or `jdx`) and optionally a molfile (extension `.mol`).

If you have [node](https://nodejs.org/en/) installed it is super easy to generate the correct json toc allowing to visualize the data from the web.

```bash
npm i --global nmrium-cli
nmrium createGeneralTOC
```

You can then publish the project on 'gh-pages' and it will be accessible directly from the browser.

https://www.nmrium.org/nmrium#?toc=https%3A%2F%2Fnmrdata.github.io%2Fsolid%2Ftoc.json

https://www.nmrium.org/nmrium#?toc=http%3A%2F%2Flocalhost:5500%2Ftoc.json

## Acknowledgements

This project has received funding from the European Union’s [Horizon 2020 research and innovation programme](https://ec.europa.eu/programmes/horizon2020/en) under grant agreement [No 957189](https://cordis.europa.eu/project/id/957189).
