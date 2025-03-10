#### Setup

```bash
npm install && npm start
```

#### Database Connection

1. Import connect.js
2. Invoke in start()
3. Setup .env in the root
4. Add MONGO_URI with correct value

#### Routers

- auth.js
- ArtCollectibles.js

#### User Model

Email Validation Regex

```regex
/^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
```

#### Register User

- Validate - name, email, password - with Mongoose
- Hash Password (with bcryptjs)
- Save User
- Generate Token
- Send Response with Token

#### Login User

- Validate - email, password - in controller
- If email or password is missing, throw BadRequestError
- Find User
- Compare Passwords
- If no user or password does not match, throw UnauthenticatedError
- If correct, generate Token
- Send Response with Token

#### Mongoose Errors

- Validation Errors
- Duplicate (Email)
- Cast Error

#### Security

- helmet = with the help of helmet we can protect our API, the most populer security packages, set different HTTP Headers to prevent numioruse attacks
- cors = Cross Origin request sharing -> by installing this package we make our API accessible to th public
- xss-clean = sanatize the user input at req.body , req.query , req.param
- express-rate-limit = limit the amount of request that user can do

Swagger UI

```yaml
/ArtCollectibles/{id}:
  parameters:
    - in: path
      name: id
      schema:
        type: string
      required: true
      description: the ArtCollectible id
```
