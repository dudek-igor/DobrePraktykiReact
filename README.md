# Dobre Praktyki w React
Dobre Praktyki w React
> Staram na bierząco uzupełniać wiadomości

### Stosować destrykturyzację wszędzie gdzie to tylko możliwe
```bash
1. const [item1, item2, ...items] = ArrayOfItems
2. const {item1, item2:{id, content}} = props
3. const FunctionComponents = ({item, log: { _id, priority, text, user, created }}) => {...........});
```



