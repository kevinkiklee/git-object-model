# Git Object Model

## Table of Contents

* Git Fundamentals
  * Git Objects
  * Directed Acyclic Graph (DAG)
  * Reference Pointer
  * Git Porcelain and Plumbing
  * Merge and Rebase
* JavaScript/Git Integration
  * `js-git`
  * `js-github`
  * Example application:
    * Pseudo-merging with ASTs
    * AST Fundamentals
    * Babel.transform()
    * Babel.transformFromAst()

# Git Fundamentals

Git is a versioning system that utilizes a DAG snapshot system, instead of a diff-based versioning system like SVN.  As the cost of storage and processing power increase, Git provides a more manageable way of versioning by creating a snapshot of everything at that exact point in time.

Every commit is the complete snapshot of the current repo.

* Git is "fundamentally a content-adressable filesystem with a VCS UI"
  * Transparency

## Git Objects
Git utilizes four distinct objects to represent information.  These objects are arranged in a graph for easy retrieval and manipulation operations.

### Blob
* Contains the content of the file.
* The identifier is a SHA1 hash, which is also its folder name.
* A file with the exact same content will have the exact same hash.

### Tree
* Contains the structure of the folder
* Can contain itself (recursive)

### Commit
* Contains the snapshot of the trees and the blobs

### Tag
* An object pointing to any object.
* Think of this as a permanent `HEAD`

## Directed Acyclic Graph (DAG)

DAG is a graph that flows one way, and cannot return to itself while traversing in that direction.  Git combines the four objects into a DAG.  The object is the data, and the DAG is the data structure.

* Information Objects
* Snapshot Objects

## Reference Pointer

* Git contains a list of reference pointers to a commit or a tag.
* `HEAD` file contains the information for the current reference pointer.  `update-ref` can be used to modify the content of the `HEAD` file.

## Git Porcelain and Plumbing

* The porcelain layer is the high-level commands utilized to manipulate the git database

* The plumbing layer is a set of low-level commands that directly modify the Git database.
* Plumbing commands aren't meant to be used on the command line, but rather to be used as building blocks for a bigger application.

* The plumbing commands provide a CRUD-like interface to the Git database.


* `cat-file`
* Blob:  `hash-object`
* Tree:  `write-tree`
* Commit:  `commit-tree`

### Update

### Delete

## Merge and Rebase

A merge is simply a commit with two or more parents.


# JavaScript/Git Integration

## `js-git` and `js-github`

## Example Application
* Pseudo-merging with ASTs
* Abstract Syntax Tree Overview
* Babel.transform()
* Babel.transformFromAst()
