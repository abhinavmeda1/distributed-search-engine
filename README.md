# Design and Implementation of a Scalable Text Search Engine

This project demonstrates the development of a high-performance, scalable text search engine using **Apache Solr** and **ZooKeeper**. The system is designed to handle high query-per-second (QPS) workloads and serves as a powerful alternative to managed search services, offering greater control and customization.

---

## ✨ Key Features

* **Scalable Architecture:** Built on SolrCloud, the engine scales horizontally to handle growing data volumes and high query loads.
* **Advanced Search Quality:** Implements full-text search, hit highlighting, faceted navigation, synonym expansion, and auto-suggest for a rich user experience.
* **Distributed Coordination:** Uses a ZooKeeper ensemble for robust cluster management, configuration synchronization, and fault tolerance.
* **Custom Admin & Search UI:** Includes a web-based interface for system monitoring and a feature-rich, AJAX-driven search interface for users.
* **Performance Benchmarked:** System performance and scalability were rigorously tested and validated using the **Siege** benchmarking tool to simulate high concurrent user traffic.

---

## 🛠️ Technology Stack

* **Search Platform:** Apache Solr (SolrCloud)
* **Coordination Service:** Apache ZooKeeper
* **Backend (Admin UI):** Spring Boot
* **Database:** PostgreSQL
* **Benchmarking Tool:** Siege

---

## 🏗️ System Architecture

The architecture is built around a distributed SolrCloud cluster coordinated by ZooKeeper. The system is modular, separating the core search functionality from the administration and search interfaces.

![System Architecture Diagram](assets/image_1745844625115_0.png)

1.  **SolrCloud Cluster:** Manages distributed indexing and search operations. The index is partitioned into **shards** across multiple nodes, enabling horizontal scaling for both data and query throughput.
2.  **ZooKeeper Ensemble:** Acts as the central coordinator, handling node discovery, leader election, and distributed configuration management to ensure high availability and cluster stability.
3.  **Admin & Monitoring Interface:** A Spring Boot application that provides a dashboard for real-time cluster monitoring, schema management, and viewing performance metrics from Siege benchmarks.
4.  **Document & Query Pipelines:**
    * **Indexing:** Documents are ingested, processed, and indexed across the Solr shards in near-real-time.
    * **Querying:** User queries are distributed and executed in parallel across shards, with results merged and ranked before being returned.

---

## ⚙️ Implementation & Configuration Highlights

### Solr Configuration

* **`schema.xml` (Schema Definition):**
    * Defines field types for strings, numbers, dates, and text.
    * The `text_general` field type uses an analysis chain with **StandardTokenizer**, **StopFilter**, **LowerCaseFilter**, and a **SynonymGraphFilter** to improve search recall.
    * Uses dynamic fields (`*_s`, `*_i`, etc.) for flexible metadata handling.

* **`solrconfig.xml` (Core Configuration):**
    * Configures request handlers for search (`/select`) and auto-suggest (`/suggest`).
    * Enables **faceting** on fields like `category` and `tags`.
    * Defines **highlighting** parameters to return relevant snippets from search results.
    * Optimizes indexing performance with settings like `ramBufferSizeMB`.

### ZooKeeper Ensemble

A three-node ZooKeeper ensemble is configured to provide fault tolerance. The configuration defines essential timing parameters (`tickTime`, `initLimit`, `syncLimit`) to ensure reliable communication and state synchronization across the Solr cluster.

---

## 🖥️ System Components

### Administration and Monitoring Interface

The Spring Boot-based admin dashboard provides a UI for managing the search cluster. It allows for dynamic schema modifications and displays key performance metrics like query throughput and indexing rates.

![Admin Dashboard Visualization](assets/image_1745833271054_0.png)

### Search Interface

The user-facing search interface is an AJAX-driven application. It features widgets for displaying results (with highlighting), pagination, faceted navigation, and auto-suggest, offering a responsive and intuitive search experience.

![User Search Interface](assets/image_1745836671405_0.png)
