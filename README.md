# Simple SQLite Clone in C

A lightweight SQLite-inspired database implementation in C, built for educational purposes. This project demonstrates fundamental database concepts including B-trees, paging, and basic SQL operations.

## Features

- Custom REPL (Read-Eval-Print Loop) interface
- Basic SQL operations (INSERT and SELECT)
- B-tree data structure for efficient data storage and retrieval
- Persistent storage with a simple file-based approach
- Memory management with paging system
- Row-based storage format

## Technical Specifications

- Row Structure:
  - ID (integer)
  - Username (varchar, max 32 chars)
  - Email (varchar, max 255 chars)
- B-tree Implementation:
  - Leaf nodes and internal nodes
  - Automatic node splitting when full
  - Parent pointer for tree traversal
- Page size: 4096 bytes
- Maximum pages: 100

## Building the Project

To compile the project, use a C compiler (gcc recommended):

```bash
gcc -o db main.c
```

## Usage

1. Start the database with a file name:
```bash
./db mydb.db
```

2. Available commands:
```sql
-- Insert a new record
insert 1 user1 user1@example.com

-- Select all records
select

-- Meta commands
.exit      -- Exit the program
.btree     -- Display the B-tree structure
.constants -- Show internal constants
```

## Running Tests

The project includes RSpec tests. To run them:

1. Install Ruby and RSpec
2. Run the test suite:
```bash
rspec spec/main_spec.rb
```

## Project Structure

- `main.c`: Main source code containing the database implementation
- `spec/main_spec.rb`: Test specifications
- `.gitignore`: Git ignore rules
- `README.md`: This documentation file

## Implementation Details

The database is implemented with the following key components:

1. **Pager**: Handles reading/writing pages to disk
2. **Table**: Manages the database structure
3. **Cursor**: Abstracts the position in the table
4. **B-tree**: Implements the tree data structure for storing rows
5. **Node**: Represents leaf and internal nodes in the B-tree

## Limitations

- Fixed schema (id, username, email)
- Basic SQL support (only INSERT and SELECT)
- No DELETE or UPDATE operations
- No transaction support
- Maximum 100 pages

## Contributing

Feel free to submit issues and enhancement requests!

## License

This project is open source and available under the MIT License.

## Acknowledgments

This project is inspired by the "Let's Build a Simple Database" tutorial series, implementing a SQLite clone from scratch in C. 