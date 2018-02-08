## docker-mmdc

Runs [mermaid-cli](https://github.com/mermaidjs/mermaid.cli) in a container for easy rendering of [Mermaid](https://mermaidjs.github.io/) diagrams.

This image is based on [Puppeteer's example](https://github.com/GoogleChrome/puppeteer/blob/master/docs/troubleshooting.md#running-puppeteer-in-docker) with a few alterations (it doesn't download language fonts and has an `entrypoint` suited to `mermaid-cli`).

### Versions

Images will be tagged with the same version of the containing mermaid-cli. 

### Usage

```bash
docker run -i --rm --cap-add=SYS_ADMIN \
    -v <dir>:/mmdc \
    luisfarzati/mmdc {options}
```

### Example

```bash
$ tree .
.
├── diagrams
│   ├── model.mmd
│   └── workflow.mmd
└── output

2 directories, 2 files

$ docker run -i --rm --cap-add=SYS_ADMIN \
    -v `pwd`:/mmdc \
    luisfarzati/mmdc \
         -i ./diagrams/workflow.mmd \
         -o ./output/workflow.png \
         -t forest
```
