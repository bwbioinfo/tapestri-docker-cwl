[![Build and Push Docker Image](https://github.com/bwbioinfo/tapestri-docker-cwl/actions/workflows/build-and-push.yml/badge.svg)](https://github.com/bwbioinfo/tapestri-docker-cwl/actions/workflows/build-and-push.yml)

# tapestri-docker-cwl

This repository provides a [Common Workflow Language (CWL)](https://www.commonwl.org/) tool for running the [Tapestri](https://missionbio.com/tapestri/) program. The tool is packaged in a Docker container, allowing it to run seamlessly on systems with Docker, Singularity, or Apptainer installed.

## Prerequisites

To use this tool, you must have the following software installed on your system:

- [CWL tool](https://github.com/common-workflow-language/cwltool)
- [Docker](https://www.docker.com/) **OR** [Singularity](https://sylabs.io/singularity/) **OR** [Apptainer](https://apptainer.org/)

## Installation

To install and run the tool, follow these steps:

1. Clone this repository to your local machine:
   ```bash
   git clone https://github.com/bwbioinfo/tapestri-docker-cwl.git
   cd tapestri-docker-cwl
   ```

2. Install Docker, if you haven't already done so.

3. Build the Docker image (optional):
   ```bash
   docker build -f docker/Dockerfile -t tapestri-docker-cwl .
   ```
   **OR** pull the pre-built Docker image:
   ```bash
   docker pull ghcr.io/bwbioinfo/tapestri-docker-cwl:latest
   ```

   > **Note:** Building or pulling the Docker image is only necessary if you intend to run the container directly.

4. Run the CWL tool with the following commands:

   **Using Docker:**
   ```bash
   cwl-runner tapestri-tool.cwl tapestri-inputs.yml
   ```

   **Using Singularity:**
   ```bash
   cwl-runner --singularity tapestri-tool.cwl tapestri-inputs.yml
   ```

   This will execute the Tapestri software on the input files defined in the `tapestri-inputs.yml` file.

## Usage

To use this tool, you must create a YAML file specifying the required inputs and parameters. An example input file (`tapestri-inputs.yml`) is provided in the `example/` directory.

### Key Files:
- **`tapestri-tool.cwl`**: The CWL definition file describing the Tapestri workflow.
- **`tapestri-inputs.yml`**: Example input YAML file specifying input files and runtime parameters.

### Example Command:
```bash
cwl-runner tapestri-tool.cwl example/tapestri-inputs.yml
```

### Outputs:
The workflow outputs will be written to an `output/` directory in your current working directory.

## Example Input File

Here is an example `tapestri-inputs.yml`:
```yaml
input_file: path/to/input.fastq
output_dir: ./output
additional_options: "--threads 4"
```

Modify this file to suit your input data and analysis requirements.

## Contributing

Contributions are welcome! Please follow the standard GitHub workflow:

1. Fork the repository.
2. Create a new branch for your changes.
3. Make your changes and commit them.
4. Push the changes to your fork.
5. Submit a pull request.

## License

This project is licensed under the [MIT License](https://github.com/bwbioinfo/tapestri-docker-cwl/blob/main/LICENSE).

## Contact

For questions or feedback, please open an issue on this repository or contact the authors via GitHub.
