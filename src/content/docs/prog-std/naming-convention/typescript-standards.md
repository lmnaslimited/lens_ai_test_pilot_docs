---
title: TypeScript Naming Conventions
---

Some naming conventions are the same in both JavaScript and TypeScript, such as the naming conventions for **local variables**, **arrays**, **dictionaries**, **constants**, and **function names**. These conventions help keep your code readable and consistent across both languages.


Here are additional naming conventions that apply specifically to TypeScript:

## 1. **Class Naming Convention**

- **Class Names**: Class names in TypeScript should follow **PascalCase** (uppercase at the start of each word).

    **Example:**
    ```ts
    class clOrder {
      constructor(orderId: number, totalAmount: number) {
        this.orderId = orderId;
        this.totalAmount = totalAmount;
      }

      fnCalculateTotal() {
        // Logic to calculate the order total
      }
    }
    ```

## 2. **Interface Naming Convention**

- **Interface Names**: Prefix the name of interfaces with `I` (following common TypeScript conventions). This is done to signify that the interface is being implemented or used for type-checking in TypeScript.

    **Example:**
    ```ts
    interface IOrder {
      orderId: number;
      status: string;
      fnCalculateTotal(): number;
    }

    class OrderImplementation implements IOrder {
      orderId: number;
      status: string;
      totalAmount: number;
      
      constructor(orderId: number, status: string, totalAmount: number) {
        this.orderId = orderId;
        this.status = status;
        this.totalAmount = totalAmount;
      }
      
      fnCalculateTotal() {
        return this.totalAmount;
      }
    }
    ```

## 3. **Type Alias Naming Convention**

- **Type Aliases**: Type aliases in TypeScript should follow **PascalCase** to maintain consistency with other types like interfaces.

    **Example:**
    ```ts
    type TorderDetails = {
      orderId: number;
      totalAmount: number;
      status: string;
    };
    ```

## 4. **Generics Naming Convention**

- **Generics**: For generics in TypeScript, use short, meaningful names like `T`, `U`, `V`, etc. You can also use more descriptive names when appropriate.

  - **`T`** → When you need a single generic type.  
  - **`T, U`** → When two types interact (e.g., mapping keys to values).  
  - **`T, U, V`** → When three types are involved (e.g., complex data structures).  
    **Example:**
    ```ts
    function fnGetArray<T>(items: T[]): T[] {
      return items;
    }

    // More descriptive naming
    function fnGetKeyValueMap<T, U>(key: T, value: U): Record<T, U> {
      return { [key]: value };
    }
    ```

## 5. **Module Naming Convention**

- **Modules**: In TypeScript, module names (such as files) should follow **kebab-case** (lowercase letters with hyphens separating words) to make the module easier to identify and import.

    **Example:**
    ```ts
    // File name
    user-profile.ts

    // Usage in code
    import { UserProfile } from './user-profile';
    ```

## Summary of Naming Conventions in LENS

| **Category**      | **Prefix**                | **Naming Convention**                                                | **Example**                                      |
|-------------------|---------------------------|----------------------------------------------------------------------|--------------------------------------------------|
| **Interface Names** | `I`                       | Prefix with `I` followed by PascalCase for interfaces                | `IOrder`                                         |
| **Type Aliases**    | PascalCase with prefix 'T'              | Type aliases should use PascalCase                                    | `TorderDetails`                                   |
| **Generics**        | Short names like `T`, `U`, `V` | Use simple, descriptive names for generic types                       | `fnGetArray<T>(items: T[]): T[]`                   |
| **Module Names**    | Kebab-case                | Use kebab-case for module file names                                  | `user-profile.ts`                                |