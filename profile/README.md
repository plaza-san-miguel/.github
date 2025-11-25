# Plaza SanMiguel Space on Github

Main projects:

🚀 Overlord: Whole PlazaSanMiguel workflows manager.

💽 Plaza-Lake: Data analytics containers.

📈 Metabase: Data exploring dashboards

🛜 sFTP Endpoints: PUCP and Camera flows.


**Infrastructure**:

⚙️ Zero downtime for high user availability.

⚙️ AI workflow integrations.

⚙️ Auto-scaling on demand.

⚙️ ETL data analytics storage automation.


<img width="2137" height="1558" alt="image" src="https://github.com/user-attachments/assets/e1d850af-2d6c-4d52-ad0f-0fea3ce6070d" />

---

```mermaid
graph TD
    subgraph Team
        I[developer]@{ shape: notch-rect }
        J[data analyst]@{ shape: notch-rect }
    end
    subgraph Apps/Services
        E[overlord]@{ shape: fr-rect }
        F[gates]@{ shape: fr-rect }
        G[…]@{ shape: fr-rect }
    end
    I -->|input| Apps/Services

    subgraph Datalake
        PostgreSQL@{ shape: cyl }
        S3@{ shape: lin-cyl }
    end
    subgraph DataAnalytics
        A[Metabase]
        B[duckdb]@{ shape: das }
        C[AWS Athena]@{ shape: das }
        A --> B
        A --> C
    end
    J -->|querying| DataAnalytics

    subgraph mutation
        D[workloads] -->|enables| H[worker]
    end
    D -->|ETL| Apps/Services

    H -->|writes| Datalake
    B -->|reads| Datalake
    C -->|reads| Datalake
```
