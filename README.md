TypeScript é uma linguagem de programação fortemente tipada que estende o JavaScript. Aqui estão os principais tipos de dados disponíveis no TypeScript:

### Tipos Primitivos

1. **`boolean`**
   - Representa valores verdadeiros (`true`) ou falsos (`false`).
   ```typescript
   let isDone: boolean = true;
   ```

2. **`number`**
   - Representa valores numéricos, incluindo inteiros e números de ponto flutuante.
   ```typescript
   let decimal: number = 6;
   let hex: number = 0xf00d;
   let binary: number = 0b1010;
   let octal: number = 0o744;
   ```

3. **`string`**
   - Representa sequências de caracteres (texto).
   ```typescript
   let color: string = "blue";
   color = 'red';
   ```

4. **`array`**
   - Representa uma lista de valores do mesmo tipo. Pode ser definido de duas maneiras:
   ```typescript
   let list: number[] = [1, 2, 3];
   let list: Array<number> = [1, 2, 3];
   ```

5. **`tuple`**
   - Representa um array com um número fixo de elementos cujos tipos são conhecidos.
   ```typescript
   let x: [string, number];
   x = ["hello", 10]; // OK
   ```

6. **`enum`**
   - Permite definir um conjunto de valores nomeados.
   ```typescript
   enum Color {Red, Green, Blue}
   let c: Color = Color.Green;
   ```

7. **`any`**
   - Representa um tipo que pode ser qualquer coisa. Útil quando não se tem certeza do tipo.
   ```typescript
   let notSure: any = 4;
   notSure = "maybe a string instead";
   notSure = false; // OK
   ```

8. **`void`**
   - Representa a ausência de um tipo. Usado normalmente em funções que não retornam um valor.
   ```typescript
   function warnUser(): void {
       console.log("This is my warning message");
   }
   ```

9. **`null` e `undefined`**
   - Representam valores que não estão definidos.
   ```typescript
   let u: undefined = undefined;
   let n: null = null;
   ```

### Tipos Avançados

1. **`never`**
   - Representa o tipo de valores que nunca ocorrem. É usado para funções que sempre lançam uma exceção ou nunca retornam.
   ```typescript
   function error(message: string): never {
       throw new Error(message);
   }
   ```

2. **`object`**
   - Representa um valor que não é um primitivo (i.e., não `number`, `string`, `boolean`, `symbol`, `null`, ou `undefined`).
   ```typescript
   let obj: object = { name: "John" };
   ```

3. **`unknown`**
   - Representa um tipo que pode ser qualquer coisa, mas, ao contrário de `any`, impõe que você verifique o tipo antes de operar com ele.
   ```typescript
   let notSure: unknown = 4;
   if (typeof notSure === "number") {
       let num: number = notSure;
   }
   ```

4. **`union`**
   - Representa um valor que pode ser de mais de um tipo.
   ```typescript
   let id: number | string;
   id = 10;
   id = "42";
   ```

5. **`intersection`**
   - Representa um valor que é a combinação de múltiplos tipos.
   ```typescript
   type A = { a: number };
   type B = { b: number };
   let ab: A & B = { a: 1, b: 2 };
   ```

6. **`type alias`**
   - Permite criar um nome para um tipo.
   ```typescript
   type Name = string;
   type NameOrNumber = Name | number;
   ```

7. **`interface`**
   - Define um contrato que uma classe ou objeto deve seguir.
   ```typescript
   interface Person {
       firstName: string;
       lastName: string;
   }

   function greet(person: Person) {
       console.log('Hello, ' + person.firstName);
   }
   ```

### Exemplos de Uso

#### Exemplos de Funções
```typescript
function add(a: number, b: number): number {
    return a + b;
}

function log(message: string): void {
    console.log(message);
}
```

#### Exemplo de Classe
```typescript
class Animal {
    name: string;
    constructor(name: string) {
        this.name = name;
    }

    move(distanceInMeters: number = 0) {
        console.log(`${this.name} moved ${distanceInMeters}m.`);
    }
}
```

Esses são os principais tipos de dados em TypeScript. Eles ajudam a garantir que seu código seja mais robusto e menos propenso a erros.
