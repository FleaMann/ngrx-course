# NgRx Actions

* An object that specifies the `type` of action being dispatched
* Optionally contains data or a payload

## Example Action

```javascript
{
  type: '[Sidenav] Show Sidenav'
}
```

## Example Action with Payload

```javascript
{
  type: '[User] Add user',
  user: Partial<User>
}
```

## `Action` Interface

While we can create simple object actions, using TypeScript we can create classes that implement the `Actions` interface.

```javascript
export enum UserActionTypes {
  AddUser: '[User] Add user',
  AddUserFail: '[User] Add user fail',
  AddUserSuccess: '[User] Add user success'
}

export class AddUserAction implements Action {
  type: UserActionTypes.AddUser;

  constructor(public user: Partial<User>) { }
}

export class AddUserFailAction implements Action {
  type: UserActionTypes.AddUserFail;

  constructor(public error: Error) { }
}

export class AddUserSuccess implements Action {
  type: UserActionTypes.AddUserSuccess;

  constructor(public user: User) { }
}
```