---
title: "Data Format: Avro vs. Protobuf vs. Parquet"
---

## Theory

### What is Data Format?

A data format is a **specific representation or arrangement of data**. It defines how information is structured, transmitted, and encoded. Data formats specify:
- **Structure**: How the data is organized. For instance, a CSV (Comma-Separated Values) file organizes data in rows and columns, where each row represents a record and each column represents a field.
- **Encoding**: The method used to convert data into a specific format for storage or transmission. For example, text can be encoded in formats like UTF-8 or ASCII.
- **Transmission**: The way data is sent from one place to another. Different data formats can affect how data is sent over networks or stored in databases.

### Proprietary File Format vs Open File Format

Proprietary file formats like those used in PostgreSQL and SQLite offer powerful features and optimizations tailored to their respective database engines. However, they also introduce challenges related to interoperability, portability, and potential vendor lock-in. 

An open file format is a publicly documented data storage specification that allows anyone to read, write, and implement the format without restrictions or licensing fees. These formats promote interoperability across different systems and applications, facilitating easier data sharing and integration. Examples include CSV (Comma-Separated Values), JSON (JavaScript Object Notation), and XML (eXtensible Markup Language). Open file formats are typically developed and maintained by communities or organizations, ensuring continuous improvement and broad support, while minimizing the risk of vendor lock-in and promoting transparency.


### Focus of this Articles

Open File Format

### The Best Serialization is No Serialization
The statement "the best serialization is no serialization" highlights an important principle in data management:
- **In-Memory Processing**: By keeping data in-memory, you can eliminate the overhead associated with serialization and deserialization. This approach is especially advantageous in scenarios where data is frequently accessed or modified, such as real-time analytics or streaming applications.
- **Performance Gains**: Avoiding serialization can significantly boost performance, as accessing in-memory data is typically faster than reading from disk or performing conversions. This can lead to reduced latency in data processing and improved response times for applications.
- **Simplicity**: Reducing or eliminating serialization simplifies application architecture. It minimizes the complexity of handling multiple data formats and reduces the need for transformations, making the system easier to maintain and debug.

## Candidates
- Protobuf: Protobuf serializes entities as messages into a binary representation. There is no standard way to write a large set of messages into a file, but for some languages like Java, there are convenience methods to read and write messages delimited by their size. Compression can be done with data stream compression manually.
- Thrift
- MessagePack
- Avro: Avro is similar to Protobuf, but also has build-in support for writing multiple entities into a file and handles separation itself. It has several compression codecs built-in which can be set per file. Java classes can be generated by Avro based on an Avro schema file and are natively supported by the Avro reader and writer implementations. Alternatively, data can be stored in GenericRecord. Both variants are included in the results below.
- Parquet: Parquet is a columnar data format. It is mainly used inside the Hadoop universe, but is available as a separate library. It still depends on hadoop-common, so the dependency footprint is significantly larger than for all other formats. It supports the schema definition files of Avro, natively supports storing multiple entities and has built-in compression which works on a per-column level, making compression very efficient. The generated Java classes from Avro can be used as well as the GenericRecord. Additionally, Parquet allows to do the (de-)serialization without Avro. The Group class demonstrates this. It is included in the results as well.
- ORC
- Arrow
- Kryo: Kryo is an object graph serialization framework. It can serialize Java objects directly, but thus only supports Java and can not be used in other languages.
- SQLite: SQLite is a well-known self-contained SQL database which is supported by many languages, including Java. It can basically be used by any database framework using JDBC. The whole database with all tables is stored in a single file. For performance comparison, a database with a single table is used and all data is retrieved with a single select.

## Metrics

- Write/Serialization Performance: Measures the time taken to serialize (or write) data to the respective format.
- File Size: Compares the file size on disk after writing the same dataset using each format.
- Read/Deserialization SPerformance: Measures the time taken to read (or deserialize) data from the respective format back into memory.
- Schema Evolution support: Evaluates how easily each format allows for changes in the schema without breaking compatibility.
- Interoperability: Assesses how well each format works with different data processing tools and libraries.


## References
- https://blog.qaware.de/posts/binary-data-format-comparison/
- https://softwaremill.com/data-serialization-tools-comparison-avro-vs-protobuf/