# WorkOutBaby
- [X] Replace "WEB system" with your system name

## Description
- [X] Provide WEB system description in few sentences - its purpose, users, etc.
- The main aim of this system is to help to schedule a proper work out. You can set your exercises by day, learn new excercises by browsing the system and follow your progress. Main users of this system is going to be people that like to spend their time at gym/outdoors and staying fit. 
## Entity definition

   Exercise: id(number(length=10000)), category(string(length=100) OR number(length=10000)), description(string(length=100000)), date_posted(date), image, likes(number(length>0)).
- [ ] Define the entity ("object" that will be manipulated) of WEB system
- [ ] Entity should have a name
- [ ] Entity should have 3 mandatory attributes:
    - [ ] ID - depending on specific service this could be a number or string
    - [ ] Creation date - (if applicable for specific service) ISO 8601 format date string
    - [ ] Modification date - (if applicable for specific service) ISO 8601 format date string
- [ ] Entity should have at least 5 custom attributes
    - [ ] Each attribute should have a type defined: number, string, ISO 8601 date string, boolean, object, array or other
    - [ ] Each attribute should have restrictions defined: list of constants, or number range, or string length, or string format, or object schema, or array schema or other. For example, you can use `joi` language to define restrictions: https://github.com/hapijs/joi/blob/v13.1.2/API.md

## API definition
   - Get exercise: GET /api/exercise/:id/
      400 - {error: 'invalid exercise ID'}
   - Post like: POST /api/exercise/:id/like
      400 - {error: 'invalid exercise ID'}
   - Get exercises by day: GET /api/day/:id/exercise
      400 - {error: 'invalid day ID'}
   - Get exercise image: GET /api/exercise/:id/image
      400 - {error: 'invalid image ID'}
   - 404 - {error: 'page not found'}
   - 500 - {error: 'server error'}




- [ ] Define specific service (konkrečios paslaugos) API methods that WEB system is going to use
- [ ] Optionally define additional API methods that WEB system is going to expose
- [ ] API should have at least 4 methods
    - [ ] A method to return entity by ID. Should not have request body
    - [ ] A method to return multiple entities (Array) by ID. This method should support at least one header value to:
        - [ ] Return only entities that match pattern in one of its attributes
        - [ ] Return 10 entities starting provided index
        - [ ] Return sorted entities by one of its attributes (both ascending and descending)
        - [ ] Other (should be approved by Product Owner (PO))
    - [ ] A method to remove entity by ID. Returns removed entity. Should not have request body
    - [ ] A method to update entity by ID. Accepts entity to update and returns updated entity
- [ ] Each method should have HTTP method defined
- [ ] Each method should have URI defined (use {id} as entity ID placeholder)
- [ ] Should return all 4xx errors in unified format. Define format using `joi` language
- [ ] Should return all 5xx errors in unified format. Define format using `joi` language

## UI definition

   https://wireframe.cc/aev1fO
- [ ] Define the structure of how visually the WEB system is going to look like
- [ ] Should have at least one view defined with https://wireframe.cc (or other wireframe tool):
- [ ] The view should have a title
- [ ] The view should have a description of a service provided by web system
- [ ] The view should include at least 2 UI components:
    - [ ] A component to display multiple entities with all their attribute values visible. It should be posible to remove and edit selected entity.
        - [ ] Depending on chosen header of API method that returns multiple entities, it should be posible to select specific 10 entities starting index, sort entities by attribute, filter entities by attribute pattern, or other (should be approved by Product Owner (PO))
    - [ ] A component to create a new entity/edit existing entity. It should be posbile to create new entity and edit selected entity
        - [ ] Each attribute should have a dedicated editor field: text box for string or number, checkbox or radio buttons for boolean, date picker for date, etc.
