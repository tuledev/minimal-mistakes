# React

[https://vasanthk.gitbooks.io/react-bits/patterns/25.presentational-vs-container.html](https://vasanthk.gitbooks.io/react-bits/patterns/25.presentational-vs-container.html)  
Presentational just have props -&gt; func component  
Container pass state + props -&gt; Presentational

[https://vasanthk.gitbooks.io/react-bits/patterns/27.passing-function-to-setState.html](https://vasanthk.gitbooks.io/react-bits/patterns/27.passing-function-to-setState.html)  
Pass func to setState

[https://vasanthk.gitbooks.io/react-bits/anti-patterns/01.props-in-initial-state.html](https://vasanthk.gitbooks.io/react-bits/anti-patterns/01.props-in-initial-state.html)  
Avoid to setState in constructor with props  
  
[https://vasanthk.gitbooks.io/react-bits/anti-patterns/04.setState-in-componentWillMount.html](https://vasanthk.gitbooks.io/react-bits/anti-patterns/04.setState-in-componentWillMount.html)  
Should call setState in componentDidMount  
  
[https://vasanthk.gitbooks.io/react-bits/anti-patterns/05.mutating-state.html](https://vasanthk.gitbooks.io/react-bits/anti-patterns/05.mutating-state.html)  
Don't mutating state without setState. Whenever setState gets called in the future, the mutated state gets applied

[https://vasanthk.gitbooks.io/react-bits/anti-patterns/06.using-indexes-as-key.html](https://vasanthk.gitbooks.io/react-bits/anti-patterns/06.using-indexes-as-key.html)  
Don't use index as key

