# Dubbo Python Serialization Enhancement

## Overview
This repository contains sample code and contributions for enhancing **serialization in Dubbo Python** using **Pydantic with JSON and Protobuf support**. The goal is to improve data validation, performance, and ease of use for serialization in **Dubbo Python RPC**.

## Motivation
Dubbo Python currently requires users to implement custom serialization methods. This project aims to:
- **Standardize serialization** by providing built-in support for JSON and Protobuf.
- **Improve data validation** using Pydantic schemas.
- **Enhance performance** by optimizing serialization mechanisms.
- **Simplify configuration** for developers using Dubbo Python.

## Proposed Approach
### Current Serialization (Manual Handling)
```python
import json

def serialize(data):
    return json.dumps(data)

def deserialize(data):
    return json.loads(data)
```

### Enhanced Serialization (Pydantic-based)
```python
from pydantic import BaseModel

class User(BaseModel):
    name: str
    age: int

def serialize(data: User):
    return data.json()

def deserialize(data):
    return User.parse_raw(data)
```

### Expected Benefits
- **Automatic data validation** with Pydantic.
- **Standardized serialization format** for JSON and Protobuf.
- **Performance improvements** through optimized serialization logic.

## Contribution - Early Work
This repository contains:
- **Sample Pydantic-based serialization module.**
- **Unit tests for serialization and deserialization.**
- **Performance benchmarks comparing old vs. new serialization.**
- **Documentation on how to integrate serialization into Dubbo Python.**

## How to Use
1. Clone this repository:
   ```sh
   git clone https://github.com/YOUR_GITHUB_USERNAME/dubbo-python-serialization.git
   cd dubbo-python-serialization
   ```
2. Install dependencies:
   ```sh
   pip install pydantic protobuf
   ```
3. Run the sample serialization script:
   ```sh
   python serialize_example.py
   ```
4. Run unit tests:
   ```sh
   pytest tests/
   ```

## Related Links
- **[Dubbo Python Repository](https://github.com/apache/dubbo-python)**
- **[Pydantic Documentation](https://docs.pydantic.dev/)**
- **[Protobuf Documentation](https://protobuf.dev/)**

## License
This project follows the Apache 2.0 License.

---

This repository is part of my **Google Summer of Code 2025** application for contributing to the **Dubbo Python project** by implementing an enhanced serialization system. 🚀
