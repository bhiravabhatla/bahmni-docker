# Bahmni-Docker
Dockerfile and resources to create Docker images for Bahmni

### Building a new image
This repository comes with a set of preset profiles to create a new Bahmni Docker image for the most common components used. See the [./inventories](./inventories) folder for a list of all inventory files available.
If the existing inventory files don't suit to your need, you can manually create a new one and start the image based on it.

#### Run the Docker build to build the new image
To build the Bahmni Docker image, just run the following instructions :
```
git clone https://github.com/mekomsolutions/bahmni-docker.git
cd bahmni-docker/
docker build --build-arg INVENTORY_FILE=[file_name] ./ -t mekomsolutions/bahmni:[file_name]_[commit_id]
```

where:
- [file_name] is the name of the inventory file from inventories/ folder
- [commit_id] is the 7 first digits of your current commit.

### Push the newly built image, if needed

To push the newly built Docker image:
```
docker push mekomsolutions/bahmni:[inventory_profile]_[commit_id]
```

Note that you would need to have logged in using `docker login` first