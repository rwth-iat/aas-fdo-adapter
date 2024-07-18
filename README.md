# AAS-FDO-Adapter
This is a simple adapter that allows you to automatically generate FDO from AAS.
This is based on the [basyx-python-SDK](https://github.com/rwth-iat/basyx-python-sdk) and the generated client for [FDO-Manager-Service](https://gitlab.indiscale.com/fdo/fdo-manager-service/-/tree/main?ref_type=heads)

## Installation
1. To install the adapter, we should first generate the client for the FDO-Manager-Service. The instructions to generate the client can be found [here](https://gitlab.indiscale.com/fdo/fdo-manager-clients/-/tree/main/example-client?ref_type=heads).
1. After generating the client, add the generated client module to your python environment:
    ```bash
    pip install <path-to-generated-client>
    ```
1. Install the adapter:
    ```bash
    pip install git+https://github.com/rwth-iat/aas-fdo-adapter.git
    ```

## Usage
For usage examples, please refer to the [example.py](example.py) file.

