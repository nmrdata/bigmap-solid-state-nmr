![logo](images/nmrium-logo.svg)

# Solid state NMR visualization

## Short summary

The goal of this project is to provide an open source microservice (app) for the visualization and analysis of solid-state NMR data accessible via a modern web front-end (React).

The project is open-source (MIT license) and is available on [https://git.nmrium.org](https://git.nmrium.org). An exhaustive documentation can be found on [https://docs.nmrium.org](https://docs.nmrium.org).

In order to show the possibilities, we provide here a solid state NMR dataset.
It can be previewed from this link [https://www.nmrium.org/nmrium#?toc=https%3A%2F%2Fnmrdata.github.io%2Fbigmap-solid-state-nmr%2Ftoc.json](https://www.nmrium.org/nmrium#?toc=https%3A%2F%2Fnmrdata.github.io%2Fbigmap-solid-state-nmr%2Ftoc.json).

![overview](images/overview.png)

## Integration in your own React website

`NMRium` is published on `npm` and can be installed using:

`npm i nmrium`

It can then be included in your `jsx` component using the following syntax:

```jsx
import NMRium from "nmrium";

function MyComponent() {
  return <NMRium />;
}
```

More information about loading the data and using the numerous options can be found [https://docs.nmrium.org/for-developers/include-react-component](https://docs.nmrium.org/for-developers/include-react-component).

## Visualization of data on [https://www.nmrium.org/nmrium](https://www.nmrium.org/nmrium)

The website [https://www.nmrium.org/nmrium](https://www.nmrium.org/nmrium) provides a demonstration of NMRium component. On this page you are able either to drag and drop a list of JCAMP-DX files or a zip file containing native Bruker files.

The usage of the React component is extensively described on [https://docs.nmrium.org](https://docs.nmrium.org).

## Opening directly your spectra from your ELN on [https://www.nmrium.org](https://www.nmrium.org)

The website [www.nmrium.org](https://www.nmrium.org/) is able to load a Table Of Contents (TOC) as a JSON file.

If you would like to have a menu on the left containing many group of spectra you should load a correctly formatted `.json` file. In this case the URL has the following structure:

<kbd>https://www.nmrium.org/nmrium</kbd><kbd>#?json=</kbd><kbd>jsonURL</kbd>

The `jsonURL` must be accessible using Ajax (take care about cross-origin).

Here is an example of the content of the `toc.json` file:

```json
[
  {
    "groupName": "CAM.26025",
    "folderName": "CAM.26025",
    "children": [
      {
        "id": "f3oJnR1zqfNNffI0Urjkf1oZifc=",
        "file": "./CAM.26025/broadband/index.json",
        "title": "broadband",
        "selected": true
      },
      {
        "id": "gcVdupbPgszMCpSM3lPoS/AcG3c=",
        "file": "./CAM.26025/matpass/index.json",
        "title": "matpass"
      },
      {
        "id": "t87E7IvM5VKHAEjtX1Q2HCB23d4=",
        "file": "./CAM.26025/selective/index.json",
        "title": "selective"
      }
    ]
  }
]
```

The `file` attribute will contain the relative link to an NMRium file (encodes as a JSON) that describes the set of JCAMP-DX to load. Here is for example the content of the file `./CAM.26025/broadband/index.json`:

```json
{
  "spectra": [
    {
      "source": {
        "jcampURL": "./17O_NMR_La17Sr03NiO4_broadband-spinecho.dx"
      },
      "display": {
        "name": "17O_NMR_La17Sr03NiO4_broadband-spinecho.dx"
      }
    },
    {
      "source": {
        "jcampURL": "./17O_NMR_La18Sr02NiO4_broadband-spinecho.dx"
      },
      "display": {
        "name": "17O_NMR_La18Sr02NiO4_broadband-spinecho.dx"
      }
    },
    {
      "source": {
        "jcampURL": "./17O_NMR_La19Sr01NiO4_broadband-spinecho.dx"
      },
      "display": {
        "name": "17O_NMR_La19Sr01NiO4_broadband-spinecho.dx"
      }
    },
    {
      "source": {
        "jcampURL": "./17O_NMR_La2NiO4_broadband-spinecho.dx"
      },
      "display": {
        "name": "17O_NMR_La2NiO4_broadband-spinecho.dx"
      }
    }
  ]
}
```

This example can be tested here:
[https://www.nmrium.org/nmrium#?toc=https%3A%2F%2Fcheminfo.github.io%2Fnmr-dataset3%2Fmultiplet%2Findex.json](https://www.nmrium.org/nmrium#?toc=https%3A%2F%2Fcheminfo.github.io%2Fnmr-dataset3%2Fmultiplet%2Findex.json)

More information can be found on [https://docs.nmrium.org/for-developers/using-nmrium#loading-a-table-of-contents](https://docs.nmrium.org/for-developers/using-nmrium#loading-a-table-of-contents).

## Creating your own databaset

We have develop a utility that simplifies the process of creating a static set of spectra and the toc.json file.

The principle is quite simple, you create folders containing jcamp files (extension `dx` or `jdx`) and optionally a molfile (extension `.mol`).

If you have [node](https://nodejs.org/en/) installed it is super easy to generate the correct json toc allowing to visualize the data from the web.

```bash
npm i --global nmrium-cli
nmrium createGeneralTOC
```

This command will generate the required `toc.json` file as well as the corresponding `.json` in each folder. If this `toc.json` is accessible from a URL it can be loaded by NMRium as explained above.

## Acknowledgements

This project has received funding from the European Union’s [Horizon 2020 research and innovation programme](https://ec.europa.eu/programmes/horizon2020/en) under grant agreement [No 957189](https://cordis.europa.eu/project/id/957189).
