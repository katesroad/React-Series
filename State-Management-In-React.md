
# State Management in React

## About

-  This is a note for talk [Managing Application State Management-Talk By Kent C.Dodds](https://www.youtube.com/watch?v=zpUMRsAO6-Y&ab_channel=freeCodeCampTalks)
- Slides material link [application-state-management-talk](https://github.com/kentcdodds/application-state-management-talk/tree/main/slides)

##  State management in React

###  What is React
A UI state management library, data driven UI solution

```tsx
interface CounterProps {
  step?: number;
  start?: number;
}

const Counter: React.FC<CounterProps> = ({step = 0, start = 0}) => {
   const [count, setCounte] = React.useState<number>(start);
   
   const handleClick = () => {
	   setCount(count => count + step);
   };
   
   return <button onClick={handleClick}>{count}</button>
};
```

### What is state
- what is state
	- Data changes overtime
	- .ie, things change on server side, we need to make other application state change
- A couple of ways to simplify the state management
	- **Two category of states are there at frontend side**
		- Server cache
State that's actually stored on the server and we store in the client side for quick-access(like user data) for performance reason
		- UI state
State that's only useful in the UI controlling the interactive parts of our app(like modal isOpen state)
	- [ The state management Mistake](https://epicreact.dev/my-state-management-mistake/)
- Some solutions for caching the server side state at the front end side
	- React-Query, a server side state cache solution for React
	- Remix.run, https://remix.run
- The UI state
	- What is global state
		- The more state to be put at global for your application, the more complex the application  global statege will be overtime
		- Potential brought by
			- Redux
			- React Context
	- React is a state management library for UI
		- state management
		- Share state across components -> state up to their least common shared parents -> state drilling
			- Is this state being used more than two places?
			- Arguments, props drilling is not always problem, but can be annoying
		 - Possible solution for props-drilling are
			 - component composition(Slots concepts borrowed from Vue)
			 - React context
				- [An example of breaking global context](https://youtu.be/zpUMRsAO6-Y?t=1455)
			- Collocation
				- code splitting just works
				- File structure scales well
				- Reduced indirection
			- Still have performance issue
				- recoil
				- jotai

## Summary

- props drilling
	- is not a problem
	- solution
		- compostion
			- Pass react elements
			- Composition
			- using react context
- Seperate Application state
	- UI state
	- Server side cache
- Collocation to solve context
- Cohesive
	- not every hooks should be global

