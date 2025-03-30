# Spark Sandbox in a DevContainer

This repository provides a ready-to-use development environment for a Spark cluster inside a **DevContainer**. It includes all necessary configurations and Python libraries to get started quickly with Apache Spark.

## Features

- Pre-configured **Apache Spark** cluster
- Python libraries for working with Spark (e.g., `pyspark`, `pandas`, `numpy`)
- **DevContainer** setup for seamless development using VS Code or GitHub Codespaces

## Getting Started

### Prerequisites

- Install **Docker**
- Install **VS Code** with the **Dev Containers** extension

### Setup

1. Clone this repository:
   ```sh
   git clone https://github.com/ezulfica/pySpark-sandbox.git
   cd pySpark-sandbox
   ```
2. Open in VS Code and reopen in a container when prompted.

### Using Spark

- Open a terminal inside the DevContainer and start using **PySpark**:
  ```sh
  pyspark
  ```
- Run Python scripts inside the container with Spark support:
  ```sh
  python your_script.py
  ```

## Folder Structure

```
/
├── .devcontainer/        # DevContainer configuration
│   ├── devcontainer.json
│   ├── Dockerfile
│   ├── docker-compose.yml
├── .dockerignore         # Docker ignore file
├── .git/                 # Git repository metadata
├── .gitignore            # Git ignore file
├── spark-config/         # Spark configuration files
├── spark-data/           # Spark data storage
├── spark-events/         # Spark event logs
├── pyproject.toml        # Python project configuration
├── README.md             # This file
```

## Contributing

Feel free to submit issues or pull requests to improve this sandbox.

## License

This project is licensed under the MIT License.

