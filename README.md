## Elastic cluster compose

This repository contains a simple setup to run an Elasticsearch cluster with Kibana using Docker Compose.

This has been created using https://www.elastic.co/docs/deploy-manage/deploy/self-managed/install-elasticsearch-docker-compose

Note that you can also use [Elastic Cloud](https://www.elastic.co/cloud/) or [Bonzai](https://bonsai.io/) to try out ELK stack without any local setup.

### Prerequisites

- [Docker Desktop](https://www.docker.com/products/docker-desktop/) installed

### Single Node cluster

1. Clone the repo and navigate to the project directory
2. Then, you can create the single node cluster using the command:

```bash
docker compose -f compose-single-node.yml up -d
```

Then you need to wait few minutes for the cluster to be ready

### Multi-Node cluster

1. Clone the repo and navigate to the project directory
2. Once done, you need to create a custom `.env` file based on the `.env.example` file
3. Then, you can create the elastic cluster using the command:

```bash
docker compose up -d
```

Then you need to wait few minutes for the cluster to be ready

4. Once the cluster is ready, you can access:
   - Kibana at: https://localhost:5601 with `elastic` user and the password you set in the `.env` file
   - Elasticsearch at: https://localhost:9200 with `elastic` user and the password you set in the `.env` file


### Add Sample Web logs

You can add sample data to Elasticsearch by:

1. Connect to kibana web UI
2. Go to `Home/Add Integrations/Sample Data`
3. Click on `Other sample data sets` and then under Sample Web logs: `Add data`
4. You should see the data in the `kibana_sample_data_logs` index

### Stopping the cluster

To stop and remove the elastic cluster containers, run:

```bash
docker compose down
```
