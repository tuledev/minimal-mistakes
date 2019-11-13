# Tips

1. Container and presenter
2. Reselect
3. Cache createAnimatedComponent
4. Connect to redux in the wanted specific component
5. PureComponent first
6. shouldComponentUpdate
7. Pure render
   1. Avoid init {}, \[\] in passed props. Using package var  
      ~~`<Component items={data || []}>`~~

      `<Component items={data || EmptyData}>`

   2. Avoid init arrow func in passed props
8. requestAnimationFrame
9. 
