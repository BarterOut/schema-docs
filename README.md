# BarterOut API Schema Documentation

## Overview
This documentation is here to provide you information on our data models used in our database,
and therefore our API, which you are presumably doing.

### User Models

#### User
```
{
  emailAddress: { type: String, unique: true, required: true },
  password: { type: String, required: true },
  venmoUsername: { type: String, required: true },
  CMC: { type: String, required: true },
  firstName: { type: String, required: true },
  lastName: { type: String, required: true },
  university: { type: String, required: true },
  permissionType: { type: Number, required: true, default: 0 },
  numberOfBooksSold: { type: Number, default: 0 },
  numberOfBooksBought: { type: Number, default: 0 },
  moneyMade: { type: Number, default: 0 },
  matchedBooks: [{ type: String }],
  cart: [{ type: String }],
  notifications: [{
    date: String,
    message: String,
  }],
  resetPasswordToken: { type: String },
  resetPasswordExpires: { type: Date },
}
```

#### Temp User
```
{
  emailAddress: { type: 'String', unique: true, required: true },
  password: { type: 'String', required: true },
  venmoUsername: { type: 'String', required: true },
  CMC: { type: 'String', required: true },
  firstName: { type: 'String', required: true },
  lastName: { type: 'String', required: true },
  matchedBooks: [{ type: String }],
  university: { type: 'String', required: true },
  emailToken: { type: 'String', required: true },
  createdAt: {
    type: Date, expires: '24h', default: Date.now(), required: true,
  },
}
```

### Books

#### Textbook Up for Sale (generic)
```
{
  name: { type: 'String', required: true },
  edition: { type: 'Number', required: true },
  course: { type: 'String', required: true },
  price: { type: 'Number', required: true },
  status: { type: 'Number', required: true },
  ISBN: { type: 'Number', required: false },
  condition: { type: 'String', required: true },
  owner: { type: 'String', required: true },
  comments: { type: 'String', required: false },
  date: { type: 'Number', required: true },
  buyer: { type: 'String', required: false, default: '' },
}
```
