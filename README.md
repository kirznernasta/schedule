# Schedule
Project "University schedule" for subject "Data Models and Database Management Systems"

## Kirzner Anastasiya, 153502
---
### Functional requirements:
* user authorization
* user management (CRUD)
* role system
* logging of user actions
* schedule management (CRUD)
* class management (CRUD)
* teacher management (CRUD)
* search and filter
* favorite schedule selection
* quick access

---
### Entities:
1. `User`:
   * **id** (int, not null, pk)
   * **email** (string, not null)
   * **is_admin** (bool, not null)
   * **group** (int, nullable) -> `Group`
2. `Group`:
   * **id** (int, not null, pk)
   * **number** (int, not null)
   * **faculty** (int, not null) -> `Faculty`
   * **course** (int, not null)
3. `Faculty`:
   * **id** (int, not null, pk)
   * **code_number** (smallint, not null)
   * **name** (linestring, not null)
   * **short_name** (linestring, not null)
4. `ClassRoom`:
   * **id** (int, not null, pk)
   * **number** (int, not null)
   * **building** (int, not null)
5. `Teacher`:
   * **id** (int, not null, pk)
   * **name** (linestring, not null)
   * **last_name** (linestring, not null)
6. `Subject`:
   * **id** (int, not null, pk)
   * **name** (linestring, not null)
   * **short_name** (linestring, not null)
7. `ClassType`:
   * **id** (int, not null, pk)
   * **type** (linestring, not null)
   * **color** (linestring, not null)
8. `Comment`:
   * **id** (int, not null, pk)
   * **message** (linestring, not null)
   * **date** (date, not null)
9. `Class`:
   * **id** (int, not null, pk)
   * **class_room** (int, not null) -> `Class`
   * **teacher** (int, not null) -> `Teacher`
   * **subject** (int, not null) -> `Subject`
   * **type** (int, not null) -> `Type`
   * **start_time** (time, not null)
   * **end_time** (time, not null)
   * **day_of_week** (smallint, not null)
   * **week_number** (smallint, not null)
   * **comment** (int, nullable) -> `Comment`
10. `Schedule`:
    * **id** (int, not null, pk)
    * **group** (int, not null) -> `Group`
    * **start** (date, not null)
    * **end** (date, not null)

---
