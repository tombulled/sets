# sets
Store and manage a collection of sets

## Usage
```python
import sets, pydantic, typing

class User(pydantic.BaseModel):
    name:  str
    age:   int
    hobby: typing.Optional[str]

sam = User \
(
    name = 'Sam',
    age  = 23,
)

ben = User \
(
    name  = 'Ben',
    age   = 47,
    hobby = 'painting',
)

class Users(sets.Sets[User]): pass

users = Users \
(
    name = {sam.name, ben.name},
    age  = {sam.age,  ben.age},
)
```
