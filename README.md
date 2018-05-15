# Git Object Model

## Table of Contents

* Git Fundamentals
  * Git Objects
  * Directed Acyclic Graph (DAG)
  * Reference Pointer
  * Merge and Rebase
  * Git Porcelain and Plumbing
  * Plumbing Commands
* JavaScript/Git Integration
  * `js-git`
  * `js-github`
  * Example application:
    * Pseudo-merging with ASTs
    * AST Fundamentals
    * Babel.transform()
    * Babel.transformFromAst()

# Git Fundamentals

Git is a versioning system that utilizes a DAG snapshot system instead of a diff-based versioning system such as SVN.  As the cost of storage and processing power increase, Git provided a more powerful way of versioning by creating a snapshot of every single thing at that exact point in time.

Every commit is the complete snapshot of the current repo.

## Git Objects

### Blob
- Contains the content of the file
- It's identifier, which is its filename, is a SHA1 hash
- A file with the exact same content will have the exact same hash

### Tree
- Contains the structure of the folder
- Can contain itself (recursive)

### Commit
- Contains the snapshot of the trees and the blobs

### Tag
- An object pointing to any object.
- Can point to any object.

## Directed Acyclic Graph (DAG)

A DAG is a graph that flows one way, and cannot return to itself while traversing in that direction.  Git combines the four objects into a DAG.  The object is the data, and the DAG is the data structure.

Blob/Tree - Information Objects
Commit/Tag - Snapshot Objects

## Reference Pointer

Git contains a list of reference pointers to a commit or a tag.

`HEAD` file contains the information for the current reference pointer.  `update-ref` can be used to modify the content of the `HEAD` file.

## Merge and Rebase

A merge is simply a commit with two or more parents.

## Git Porcelain and Plumbing

- The porcelain layer is the high-level commands utilized to manipulate the git database
- The plumbing layer is a set of low-level commands that directly modify the Git database.

## Git Plumbing
- The plumbing commands provide a CRUD interface to the Git database.

# JavaScript/Git Integration

## `js-git` and `js-github`

## Example Application
* Pseudo-merging with ASTs
* Abstract Syntax Tree Overview
* Babel.transform()
* Babel.transformFromAst()
