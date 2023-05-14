# TrelloApiPostman
## What is this repository for?
Practicing API testing using Postman for https://api.trello.com

This repo contains Postman collection on how to create Trello Board


Steps taken: 

- POST Create Board
- GET Get My Board
- DEL Delete Board
- GET Create Board ID
- POST Create List DONE
- POST Create List TO DO
- POST Create A Card On The List
- PUT Move a Card to Done List
- PUT Move a Card back to TO DO List
- POST Add a Comment to a Card

## How to run tests?

Using Postman Collection Runner 

```javascript

Tests done in Postman for each step

POST Create Board 

const jsonData = pm.response.json();

pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});


pm.test("Verify board type", function () {
        pm.expect(jsonData.closed).to.eql(false);
        pm.expect(jsonData.prefs.permissionLevel).to.eql("private");
});

pm.test("Verify board name", function () {
        pm.expect(jsonData.name).to.eql(pm.collectionVariables.get("BoardName"));
});

pm.collectionVariables.set("idBoard", jsonData.id)

GET Get My Board

const jsonData = pm.response.json();

pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});


pm.test("Verify board type", function () {
        pm.expect(jsonData.closed).to.eql(false);
        pm.expect(jsonData.prefs.permissionLevel).to.eql("private");
});

pm.test("Verify board name", function () {
        pm.expect(jsonData.name).to.eql(pm.collectionVariables.get("BoardName"));
});

DEL Delete Board

const jsonData = pm.response.json();

pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

 GET Create Board ID

 const jsonData = pm.response.json();

pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});


pm.test("Verify board type", function () {
        pm.expect(jsonData.closed).to.eql(false);
        pm.expect(jsonData.prefs.permissionLevel).to.eql("private");
});

pm.test("Verify board id", function () {
        pm.expect(jsonData.id).to.eql(pm.collectionVariables.get("idBoard"));
});


POST Create List DONE

const jsonData = pm.response.json();

pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Verify DONE List type", function () {
        pm.expect(jsonData.closed).to.eql(false);
       
});

POST Create List TO DO

const jsonData = pm.response.json();

pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Verify DONE List type", function () {
        pm.expect(jsonData.closed).to.eql(false);
       
});

pm.test("Verify DONE List type", function () {
        pm.expect(jsonData.name).to.eql("TO DO");
       
});

POST Create A Card On The List

const jsonData = pm.response.json();

pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Verify Card name on the List", function () {
        pm.expect(jsonData.name).to.eql("QA Automation");
       
});

PUT Move a Card to Done List

pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

PUT Move a Card back to TO DO List

pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

POST Add a Comment to a Card

const jsonData = pm.response.json();

pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Verify comment is written", function () {
        pm.expect(jsonData.data.text).to.eql(pm.collectionVariables.get("IdText"));

});

```
