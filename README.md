# GCR Cleaner

## Setup

1. Install the [Cloud SDK][cloud-sdk] for your operating system. Alternatively,
   you can run these commands from [Cloud Shell][cloud-shell], which has the SDK
   and other popular tools pre-installed.

1. Export your project ID as an environment variable. The rest of this setup
   assumes this environment variable is set.

   ```sh
   export PROJECT_ID="my-project"
   ```

   Note this is your project _ID_, not the project _number_ or _name_.

1. Enable the Google APIs - this only needs to be done once per project:

    ```sh
    gcloud services enable --project "${PROJECT_ID}" \
      appengine.googleapis.com \
      cloudscheduler.googleapis.com \
      run.googleapis.com
    ```

    This operation can take a few minutes, especially for recently-created
    projects.


## Start removing unused images.


`go run main.go -repo gcr.io/oceanic-hook-268813/repo-name -keep 3 --tag-filter-all .`

- Repo: Name of repo for which want to remove unused images
- keep: no of images you dont to want to be removed
