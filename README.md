# Milvus-Vectordb-Podman
Setting up Milvus in Podman running on Local.

'''
podman machine init
podman machine start
'''

### Download Milvus File
curl -sfL https://raw.githubusercontent.com/milvus-io/milvus/master/scripts/standalone_embed.sh -o standalone_embed.sh

### Start Installation
bash standalone_embed.sh start

Output:
Resolving "milvusdb/milvus" using unqualified-search registries (/etc/containers/registries.conf.d/999-podman-machine.conf)
Trying to pull docker.io/milvusdb/milvus:v2.5.5...
Getting image source signatures
Copying blob sha256:79b48655845850a86fa4381d073103ec7d06838e56ba3e2197fdca91a83f685d
Copying blob sha256:52667b6d9a2df6b49649a0fd5c2cecf26b3fe4b1cbf2ebfe833e4d5bd4f63c06
Copying blob sha256:c2459e2f6bc4089e3e1cf00d0f7121c020e1b485092a9bb12599199f54512de6
Copying blob sha256:9b10a938e28486049341cb41134e8c0c141b2e25870896c597e2a54df471acbb
Copying blob sha256:8abf38050f12d51419a9320c1f9c3df28c461a920fe1af4659df57e9b20d7907
Copying blob sha256:137689091e9b9ae14527209523cf21799f1169c162b9a5bed080af9e38fc4ba4
Copying config sha256:26be744b05bda7f061e55a169b01c21b5dd950f7b0d1678402e63149b2840c22
Writing manifest to image destination
Error: statfs /Users/prashantsharma/Documents/github/milvus/volumes/milvus: no such file or directory
Start failed.

### Make Directory
mkdir -p /Users/prashantsharma/Documents/github/milvus/volumes/milvus

### Verify Podman Connection list
podman system connection list 

### Start after creating directory
bash standalone_embed.sh start   
Wait for Milvus Starting...
Start successfully.
To change the default Milvus configuration, add your settings to the user.yaml file and then restart the service.

### Stop Milvus Service
bash standalone_embed.sh stop

### Milvus WebUI
Milvus is vector database and earlier there was no UI. As of v2.5.0, we can access Milvus Web UI using-
http://localhost:9091/webui/

## Run Milvus on Cloud
Setup Zilliz Cloud and create database-

![image](https://github.com/user-attachments/assets/c44a534b-1f9a-49a7-8469-6ff6d0d8608e)
