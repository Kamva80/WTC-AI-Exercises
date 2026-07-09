

**Name :** Kamva Emmanuel Ngwenga
**Date :** 9 July 2026

## 1. Initial vs Final Understanding 
Initially I thought the Task Manager was a web application with a database. After reading the README and exploring the codebase, I found it is a Python CLI application using `cli.py`. It uses only the Python standard library. The main components are Task, TaskStatus, TaskPriority, and commands like create, list, update.

## 2. Most Valuable Insights from Prompts
1. **Project Structure Prompt** : Helped me find the entry point `cli.py` without reading all files. 
2. **Feature Location Prompt** : Showed me to search for similar features like `--overdue` before adding new ones.
3. **Domain Model Prompt** : Helped me understand the core objects; Task, Status, Priority, DueDate.

## 3. Approach to implementing Business Rule 
**Rule** : Tasks overdue > 7 days should be marked as "abandoned" unless priority is HIGH/URGENT. 
**Files to modify** : `cli.py` - add logic to the `list --overdue` command or a new scheduler function. 
**Logic** : If `due_date < today - 7 days` AND `priority  != 4` AND `status != done`, then set `status = abandoned`. 
**Questions for the team** :
1. Should "abandoned" be a new status or just delete the task?
2. Should we notify the user before marking it abandoned?

## 4. Strategies for Future Unfamiliar Codebases
1. Start with README to understand purpose and commands. 
2. Use AI to explain the folder structure and entry point. 
3. Find 1 similar existing feature and copy that pattern. 
4. Draw a simple diagram of the main objects before coding. 
