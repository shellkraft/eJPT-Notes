
+ `Workspaces` allow you to keep track of all your hosts, scans and activities and are extremely useful when conducting penetration tests as they allow you to sort and organize your data based on the target or organization.

+ `MSFconsole` provides you with the ability to create, manage and switch between multiple `workspaces` depending on your requirements.

+ We will be using `workspaces` to organize our assessments as we progress through the course.

### How to use ?

1. Check the status of the `msfdb` - `db_status`.
2. We can check the help menu with `workspaces -h`.
3. We can check the list of workspaces with `workspace`
4. To check the data in my current workspace we can use `hosts` command.
5. Create a workspace with - `workspace -a <name>`
6. We can switch to a workspace with `workspace <name>`
7. Delete a workspace with `workspace -d <name>`
8. Rename a workspace with - `workspace -r <name_old> <name_new>`