# Azure Functions

An example Pulumi component that deploys a Typescript function to Azure Functions.

## Running the App

1.  Create a new stack:

    ```
    $ pulumi stack init azure-fn
    ```

1.  Login to Azure CLI (you will be prompted to do this during deployment if you forget this step):

    ```
    $ az login
    ```

1.  Restore NPM dependencies:

    ```
    $ npm install
    ```

1.  Build the Typescript project:

    ```
    $ npm run build
    ```

1.  Run `pulumi update` to preview and deploy changes:

    ``` 
    $ pulumi update
    Previewing changes:
    ...

    Performing changes:
    ...
    info: 9 changes performed:
        + 9 resources created
    Update duration: 1m20.493392283s
    ```

1.  Check the deployed function endpoint:

    ```
    $ pulumi stack output endpoint
    https://fn-app051a4f8b.azurewebsites.net/api/fn
    $ curl "$(pulumi stack output endpoint)"
    Greetings from Azure Functions!
    ...
    ```
