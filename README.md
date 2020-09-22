# Dobre Praktyki w React
Dobre Praktyki w React
> Staram na bierząco uzupełniać wiadomości.\
> Jeżeli znasz inne dobre praktyki, które znacząco podnoszą poziom kodu i ułatwiają prace, [skonatkuj się z mną.] \
> Z chęcią poszerze swoje choryzonty z React!

### 1. Stosować destrykturyzację wszędzie gdzie to tylko możliwe
```bash
1. const [item1, item2, ...items] = ArrayOfItems
2. const {item1, item2:{id, content}} = props
3. const FunctionComponents = ({item, log: { _id, priority, text, user, created }}) => {...........});
```

### 2. Single Source of Truth - Unikać lokalnego stanu, stosowac Redux-a/MobX-a, bądź useContext, tak by stan aplikacji zlokalizowany był w jednym miejscu.
  > lokalny stan (useState) stosować do komponentów UI.

### 3. Togglowanie stanu w kompnentach UI zamiast pisania dwóch funkcji.
```bash
-> MyComponent
.....
const [isOpen. setIsOpen] = useState(false);
.....
<button onClick={()=>setIsOpen(!isOpen)}>{isOpen ? `Close` : `Open`}</button>
```

### 4. Poprawny zgodny z konwencjami zapis:
```bash
1. HOC - withCompoenent
2. Custom Hook - useMyHook
3. nazwa komponentu z dużej litery
```

### 5. "Łapiąc" elementy w testach używamy `data-testid="sample`, a nie "łapiemy" po klasie :
```bash
test("render input element", () => {
    render(<Input />);
    expect(screen.getByTestId("sample-input")).toBeInTheDocument();
   });
 ```
 
 ### 6. Stworzyć plik jsconfig.json w głownym folderze projektu, a w nim dodać opcję bezwględnych ścieżek przy kompilacji. 
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
 
 ### 7. Funkcje wspierające(helpers lub utilits) wyeksportować do `utilits/index.js`
 
 ### 8. Single Responsibility Principle 
 > Zasada Pojedyńćzego zadania.\
 > Komponent powinnien wykonywać jak najbardziej zminimalizowaną liczbę zadań. \
 > Przejrzystość i czytelność kodu.
 
 ### 9. Obsługa błedów 
 > Stworzyć w utilits `setError(true, error)` którego odpiwiednio obsłużymy,
  ```bash
try{
  // fetch
}catch(error){
  setError(true, error)
}
 ```
 > React wychodzi z rozwiązaniem - [Error Boundarie]
 ```bash
<ErrorBoundary>
  <MyCommponent />
</ErrorBoundary>
 ```
 
 ### 10. Memonizacja - useMemo(), useCallback() lub użyć HOC jakim jest React.memo().
 > Memonizacja jest to zabieg, który ma na celu poprawić wydajność naszego kodu poprzez zapamiętywanie budowy / wartości komponentu.\
 > Jeżeli propsy bądź waartosći przekazane się nie zmienią kompnent nie będzie ponowanie renderowany.
 
 ### 11. Walidować propsy i nadaniawe domyślnych wartości
 > Poprzez PropTypes \
 > Poprzez TypeScript :heartpulse:
 
 ### 12. Nie pracować na wartościach typu string. 
 > Łatwo popełnić literówki. \
 > Jeżli potrzebujemy wartości do porównywania tworzymy plik constans.js, który przetrzymuje nam zmienne.\
 > Konwecja mówi, by pisać tego typu zmienne wielkimi literami.\
 > Jest to sygnał dla osoby czytającej nasz kod, że jest to zmienna stworzona do porównywania.
```bash
 -> `constans.js`
export const SAMPLE = 'SAMPLE'
```
 
 
 

[skonatkuj się z mną.]: https://www.linkedin.com/in/igor-dudek-96a87611a/
[Error Boundarie]: https://medium.com/swlh/understanding-reacts-error-boundaries-c15db8229d97
