# Dobre Praktyki w React
Dobre Praktyki w React
> Staram na bierząco uzupełniać wiadomości

### Stosować destrykturyzację wszędzie gdzie to tylko możliwe
```bash
1. const [item1, item2, ...items] = ArrayOfItems
2. const {item1, item2:{id, content}} = props
3. const FunctionComponents = ({item, log: { _id, priority, text, user, created }}) => {...........});
```

### Unikać lokalnego stanu, stosowac Redux-a bądź useContext, tak by stan aplikacji zlokalizowany był w jednym miejscu.
  > lokalny stan (useState) stosować do komponentów UI.

### Poprawny zgodny z konwencjami zapis:
```bash
1. HOC - withCompoenent
2. Custom Hook - useMyHook
3. nazwa komponentu z dużej litery
```
  


