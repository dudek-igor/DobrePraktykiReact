# Dobre Praktyki w React
Dobre Praktyki w React
> Staram na bierząco uzupełniać wiadomości

### 1. Stosować destrykturyzację wszędzie gdzie to tylko możliwe
```bash
1. const [item1, item2, ...items] = ArrayOfItems
2. const {item1, item2:{id, content}} = props
3. const FunctionComponents = ({item, log: { _id, priority, text, user, created }}) => {...........});
```

### 2. Unikać lokalnego stanu, stosowac Redux-a bądź useContext, tak by stan aplikacji zlokalizowany był w jednym miejscu.
  > lokalny stan (useState) stosować do komponentów UI.

### 3. Poprawny zgodny z konwencjami zapis:
```bash
1. HOC - withCompoenent
2. Custom Hook - useMyHook
3. nazwa komponentu z dużej litery
```

### 4. "Łapiąc" elementy w testach używamy `data-testid="sample`, a nie "łapiemy" po klasie :
```bash
test("render input element", () => {
    render(<Input />);
    expect(screen.getByTestId("sample-input")).toBeInTheDocument();
   });
 ```
 
 ### 5. Stworzyć plik jsconfig.json w głownym folderze projektu, a w nim dodać opcję bezwględnych ścieżek przy kompilacji. 
 ```bash
{
  "compilerOptions": {
    "baseUrl": "src"
  },
  "include": [
    "src"
  ]
}
 ```
 > można rówież w pliku .env stworzyć poniższą regułę, ale VSC wtedy nie podpowiada
```bash
NODE_PATH = src
 ```
 
 ### 6. Funkcje wspierające(helpers lub utils) wyeksportować do `utils/index.js`


