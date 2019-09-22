### Chart3React app structure

```mermaid
graph TD
A0[main app.js]-->A
A1[main props]-->A
A[app] -->B(utils)
A[app] -->C(containers)
A[app] -->D(reducers)
A-->E(actions)
A-->F(components)
A-->G(app.js)
A-->H(index.js)
A-->I(epic)
I-->I1(index.js)
B-->B1(constants)
B-->B2(seriesUtils)
C-->C1(panel type 1)
C-->C2(panel type 2)
C-->C3(panel type ...)
D-->D1(index.js)
D-->D2(reducers)
D2-->|combine|D1
E-->E1(index.js)
E-->E2(action types)
F-->F1(some components with special configs for this type app)
```

> 
>```js
>app/utils/constants
>```
> some constants only used in this type app

>
>```js
>app/utils/seriesUtils
>```
>some functions for series parse, format and so on only used in this type app

#### app works flow

```mermaid
graph TD
A0[props]-->|Initialization|A
A[app] -->|render| B(container)
B -->|sync action|C1(reducer)
B-->|async action|C2(epic)
C1-->|update state|B
C2-->|update state|B
```

