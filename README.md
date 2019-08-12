# Workshop-RXKS
An InDepth Introduction to RXJS

#### Legends   
📝 - Article  
🧠 - Important ( Must To Know )  
🚀 - Hard  
🍕 - Easy  
🐱‍👤 - New Skill  



### 📚Resource to Learn and Go through :  

#### Streams
A stream is a sequence of values / events over time.
Reactive programming is programming with streams.
Reactive stream libraries like RxJS let you:
 - create a stream from various sources
 - transform and filter a stream in different ways
 - combine multiple streams
 - and more!  
 
 ###### Resource
- [ ] [What is a Stream](https://gist.github.com/staltz/868e7e9bc2a7b8c1f754) 🍕🐱‍👤🧠
- [ ] [How to Create a Stream](https://reactive.how/fromevent)🍕🐱‍👤

#### Thinking Reactively 
First of all, free your mind and stop thinking whenever you have a event on UI what values you need to update. This is imperative thinking,
When a user clicks on a button stop thinking about which **function you have to call and which variables you need to update** because as the UI gets complex and complex you will loose track of all these variable that you have to update and it will get more exhaustive moving forward.  
You have to come up with a system which will update itself when it knows that something has changed.

##### Streams are what makes everything Reactive
Now we have established that we have to look at our application and UI in terms of Events which can happen on the UI. We have to figure out how we can operate on these events. So we use **Stream**.

###### Mostly we will use these things :
- **Subject** : Subject help us to control the values of Stream ourself. We can add values to streams, we can pick values from streams and everything. (Here we will treat streams the same way you use Arrays and Objects in Imperative Programming) 
- **Behaviour Subject** : Behavior Subject is a kind of Subject where we create a stream but we have to give it a value with something to start with.

> **Thinking Reactive is thinking in terms of Streams**

###### Three type of Streams
- **S (Source Streams)** :   
  - These streams will contain all the user interaction values.
  - Generally bound to the outputs of our dumb components
  - Source streams are mostly **subjects**
Anywhere, your user can interact with the application is a potential **Source Stream**.
Also, these actions user will perform are some sort of actions, but you have to stop thinking about these things in terms of actions but instead start thinking in terms of **Streams of Values**.

For example in case of **Search Box** -> You will think a search$ stream would make sense.  
But it's a bad example because search$ is an action more appropriate way to look at the search is in terms of searchTerm$ stream.
Now instead of action i am thinking about this stream in terms of search-term which is data. So you are not calling a function but instead passing a value in a stream.
```js
<sidebar 
    (search)="searchTerm$.next($event)">
</sidebar>
```

- **I (Intermediate Streams)** :
  - Intermediate streams are **streams** that are used to make the bridge between the **source streams and presentation streams** easier.
  - Generally these streams are made by **composing small source streams** or by **transforming some source streams** in a way which is desirable to produce a **presentation stream**
- **S (Presentation Streams)** :
  - These are the streams that our template needs to render properly.
  - We just have to look at the template and see which inputs our components expect.
  - Generally we map one presentation stream to one input but there is no hard rule to it.
###### Resource
- [ ] [How to look your application in terms of Events](https://blog.strongbrew.io/thinking-reactively-in-angular-and-rxjs/)🧠🚀🐱‍👤
- [ ] [Thinking Reactively](https://www.youtube.com/watch?v=3LKMwkuK0ZE)🧠🚀🐱‍👤


#### RxJS Operators


