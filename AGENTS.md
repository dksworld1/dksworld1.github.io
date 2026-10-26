# Agent access boundary

- Treat this repository root as the absolute boundary for all project work.
- Never access any file or directory outside this project root. This prohibition explicitly includes reading, listing, searching, inspecting metadata, resolving, copying, or modifying files outside the root.
- Keep every command's working directory inside this root. Do not use parent-directory traversal, absolute paths outside the root, or commands that inspect external locations.
- Do not follow symlinks, junctions, or other filesystem references that lead outside this root. Do not use glob patterns or scripts that could expand beyond it.
- Keep file reads and writes, generated artifacts, temporary project files, and repository operations within this root.
- If a task appears to require access outside the root, stop that part of the work and ask the user to provide the needed material inside the project root. Do not make an exception on your own.
- Apply this boundary on every turn and verify the target path remains inside the project root before accessing it.
