# CMake: Multiple Projects

Experimenting with defining CMake projects in subfolders instead of the root directory.

The directory structure:
```
multiple_projects/
├── CMakeLists.txt              <-- No project()
├── library
│   ├── CMakeLists.txt          <-- project()
│   ├── include
│   │   └── module1.h
│   └── src
│       └── module1.c
├── notes.txt
├── project1
│   ├── CMakeLists.txt          <-- project()
│   └── main.c
├── project2
│   ├── CMakeLists.txt          <-- project()
│   └── main.c
└── todo.txt
```

The problem(s):

	* Multiple end-user-facing projects evolve and must be built independently
	* Tracking the version number at the top level and for each project smells redundant
		* A change to a project requires a change to the top-level monolith
	* Projects can share common libraries
	* Adding architecture-specific custom commands bloats the build targets that are available from the high level

The solution(s):

	* Define projects() in subdirectories only
	* Track version numbers in subdirectories only
		* Projects must update in step with their dependencies

Cons:

	* Updating a common library for one project updates it for all
	* Custom command bloat may still be present

Technical bits:

	* Use CMAKE_HOME_DIRECTORY to refer to the root of the project - multiple_projects/
	* Use CMAKE_CURRENT_SOURCE_DIR or PROJECT_SOURCE_DIR within each project or library
