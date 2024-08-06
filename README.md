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

## How it works
In this adapter we implemented a special `DictObjectStore` with integrated FDO Service - `FdoServiceAasRegistryDictObjectStore`.

- The `DictObjectStore` is a simple in-memory object store that allows you to store and retrieve AAS objects by their id. The `DictObjectStore` can be used by the AAS Server to store the AAS Objects.
- The FDO Service is a service that allows you to create, update, and delete FDOs. 

We implemented `FdoServiceAasRegistryDictObjectStore`, which is a subclass of `DictObjectStore` that automatically creates, updates, or deletes FDOs based on the changes made in the AAS objects.

For example if an AAS Object is added to the `FdoServiceAasRegistryDictObjectStore`, the adapter will automatically create an FDO for this AAS Object. If the AAS Object is deleted, the adapter will delete the corresponding FDO. The Object Store has also a function to update the FDOs based on the changes made in the AAS Objects.