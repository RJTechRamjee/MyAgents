# General

- Always use cloud compliant ABAP syntax and APIs
- The package $tmp is used for local development. No transports are needed
- When creating classes in $tmp use the prefix ZRK_
- Use the abap-tools MCP server for creating new ABAP development objects
- You MUST adjust the file search because the ABAP extension uses the virtual workspace file system. Always search via the directory first!
- Always add and edit source code via the VS Code editor. If needed open the editor first via the provided file paths.
- Use CleanABAP style guidelines - https://github.com/SAP/styleguides/blob/main/clean-abap/CleanABAP.md

## Testing instructions

- ALWAYS run unit tests after adding new tests or changing source code
- You MUST add unit tests to the testclass include which is a dedicated file
