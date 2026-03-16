# Anagram Engine (BST & Template Classes)
**C++ | OOP | Binary Search Trees | Template Programming**

## Project Overview
This project is a high-performance Anagram Engine built in C++. It leverages a custom-built Binary Search Tree (BST) to organize and retrieve word sets based on their lexicographical signatures. The engine is designed using C++ templates to ensure data-type flexibility and follows strict Object-Oriented Programming (OOP) principles.

## Technical Highlights
* **Custom Binary Search Tree (BST):** Developed a fully templated `BinaryTree` class from scratch, implementing core data structure operations:
    * **Search & Insertion:** Achieved $O(\log n)$ average-case performance for word lookups and dictionary builds.
    * **Recursive Deletion:** Implemented a robust node-deletion algorithm handling three distinct cases (no children, one child, and two children via in-order successor replacement).
    * **Traversals:** Built recursive Pre-order, In-order, and Post-order traversal methods to facilitate different data export formats.
* **Lexicographic Signature Mapping:** Engineered an "Anagram Key" system where words are normalized by sorting their characters alphabetically (e.g., "cinema" and "iceman" both map to "aceimn"). This signature serves as the BST key for grouping anagrams.
* **Templated Node Architecture:** Utilized C++ template classes (`template <class T, class Y>`) to create a generic `Node` structure, allowing the BST to store any key-value pair, specifically mapping `std::string` keys to `std::list<std::string>` values.
* **Object-Oriented Design:** * **Encapsulation:** Encapsulated tree logic within the `AnagramDict` class to separate data management from the user interface.
    * **Memory Management:** Implemented a recursive destructor (`~BinaryTree`) to ensure all dynamically allocated nodes are properly deallocated, maintaining a leak-free memory profile.
* **Anagram Generator Logic:** Built the `addWord` engine to dynamically update the tree. The system checks for existing keys to append new anagrams to lists or inserts new nodes if a unique signature is detected.

## Data Structures Used
* **Binary Search Tree:** Main container for sorted signatures.
* **Linked Lists (std::list):** Used within tree nodes to store collections of words that share the same anagram key.
* **Template Classes:** Used for the underlying BST to allow for scalable and reusable code architecture.
