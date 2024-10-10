
# Neo4j Knowledge Graph for Book Recommendations

This project demonstrates how to build a knowledge graph using **Neo4j** and **Python** (via the `py2neo` library) for book recommendations based on users' preferences, author relationships, and genres. The knowledge graph allows users to like books, and based on their interests, the system recommends other books within similar genres or from the same authors.

## Features
- **Batch Insertion**: Insert multiple users, books, authors, and genres in a single transaction.
- **Relationships**: Model user preferences, book genres, and author-book relationships.
- **Recommendation System**: Get book recommendations based on:
  - Genres that users have shown interest in.
  - Authors whose books a user has liked.
- **Modular Design**: The system is built using object-oriented design for easy scalability and maintenance.

## Project Structure
- **`knowledge_graph.py`**: Contains the main implementation for creating and managing the knowledge graph using Neo4j.
- **`requirements.txt`**: Contains the list of required Python packages for the project.
- **`README.md`**: Instructions for setting up and using the project.

## Prerequisites

1. **Neo4j**:
   - Install Neo4j on your local machine. You can download it from [Neo4j Download Center](https://neo4j.com/download/).
   - Start Neo4j and ensure it's running on `localhost:7687`.
   - Set the default Neo4j username and password (usually `neo4j` and `password`).
   
2. **Python**:
   - Ensure you have Python 3.x installed on your machine.


## Usage

1. **Configure Neo4j Credentials**:
   Open the `knowledge_graph.py` file and modify the following line if your Neo4j server uses different credentials:
   ```python
   kg = KnowledgeGraph(uri="bolt://localhost:7687", user="neo4j", password="your_password")
   ```

2. **Running the Script**:
   To run the knowledge graph example, use:
   ```bash
   python knowledge_graph.py
   ```

   The script will:
   - Clear the existing graph (optional).
   - Add users, books, authors, and genres.
   - Define relationships (e.g., which user likes which book, which author wrote which book, etc.).
   - Query the graph to find books liked by a user and recommend books based on genre and author preferences.

3. **Queries**:
   The script provides sample outputs for the following operations:
   - **Books liked by a user**: Find which books a specific user has liked.
   - **Recommendations by genre**: Suggest books based on genres the user has shown interest in.
   - **Recommendations by author**: Suggest books written by authors whose books the user has liked.

4. **Customizing Data**:
   You can modify the users, books, authors, and genres in the code to create your own data set and relationships.


## Modifying the Graph

To add new users, books, authors, and genres, or to create new relationships, simply modify the code in `knowledge_graph.py`. For example, to add more users:

```python
users = ["Alice", "Bob", "Carol", "Dave"]
kg.add_users(users)
```

## Neo4j Browser

You can also explore the data visually in the Neo4j browser by opening [http://localhost:7474](http://localhost:7474) and running the following query:

```cypher
MATCH (n) RETURN n
```

This will show you all the nodes and relationships in your knowledge graph.
