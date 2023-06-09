# System Design for Front End

### How to approach system design problem

#### Frontend System Design

| Product Design | Component |
| ----------- | ----------- |
| High Level Design| Level Low Level Design |

---

#### Clearify the question: 
1. What is the goal of this feature?
2. Who do you building this for?
3. Do you want a generic component?

### General Plan: 
1. Functional Requirements
2. Non Functional Requirements
3. Components Archetecture
4. Props & Events
5. Performance
6. Accessibility

### Example of Requirement:

| Functional Requirements | Searchbox|
| ----------- | ----------- |
| Show suggestions on user input | When user is typing he get some feedback results in the input field |
| Debounce when user stop typing | to avoid making many network calls |
| Search results should be customizable | You build a generic component with one design library so all searches looks uniformed|
| Support both static data and data coming from an API | Is the data on client?, is it on a server?  |

---

### Non Functional Requirements:

| Non Functional Requirements |
| ----------- | ----------- |
| Network Efficient |
| Should be configurable with cache|
| Search results should be customizable | 
| Support both static data and data coming from an API |

---
## Searchbox componet architecture:

![component](/imges/component-Arc.jpg "component")

### Show more results is a return call from the API and you can present it as a scroll, pagination and maybe limit the results to a set number.

## API for Searchbox Suggestion:

![component](/imges/api.jpg "api component")


```js
getSuggesion(searchQuery, numberOfResults)

type Suggestions: Array<Suggesion>;

type Suggesion = {
  id: string;
  text: string;
  imgUrl?: string;
}

```

---

## How the consumer will use to consume the data from the widget:

 __Examples of props to be used with <Autocomplete /> component__
 
```js

<Autocomplete
  queryFn: (query) => data[]
  minResultNumber: Number
  maxResultNumber: Number
  loadingState: string | JSX.Element
  onLoad: Promise<void>
  onClose: () => void
  onClear: => void;
  onESCKey = () => void
  onChange = (e: Event) => setState(e.target.value) 
  debounce: () => void;
  showMoreResults: () => void;
/>
```

### Data flow from backend to frontend

 - how data is connected from backend and consumed by the front end app?
 - what kind of packages you may want to consider at the front end?
 - 






