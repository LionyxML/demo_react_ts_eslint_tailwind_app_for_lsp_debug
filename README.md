This is a [Next.js](https://nextjs.org) project bootstrapped with [`create-next-app`](https://nextjs.org/docs/app/api-reference/cli/create-next-app).

## Installing

Clone this repo and run `pnpm install`.

## BUGS

This is here so we can debug lsp server/clients on projects using:

- typescript
- eslint
- tailwindcss

Open `app/page.tsx`...

### Diagnostics

You should see the folling list of problems.

```text
    ~/temp/demo_react_ts_eslint_tailwind_app/app/  10
   └╴  page.tsx  10
     ├╴w  'typeX' is defined but never used. eslint (@typescript-eslint/no-unused-vars) [3, 6]
     ├╴w  'unusabled_variable' is assigned a value but never used. eslint (@typescript-eslint/no-unused-vars) [6, 9]
     ├╴w  'gap-6' applies the same CSS properties as 'gap-6'.  (cssConflict) [19, 25]
     ├╴w  'gap-6' applies the same CSS properties as 'gap-6'.  (cssConflict) [19, 58]
     ├╴w  The class `md:w-[158px]` can be written as `md:w-39.5`  (suggestCanonicalClasses) [43, 181]
     ├╴w  The class `border-black/[.08]` can be written as `border-black/8`  (suggestCanonicalClasses) [58, 102]
     ├╴w  The class `hover:bg-black/[.04]` can be written as `hover:bg-black/4`  (suggestCanonicalClasses) [58, 169]
     ├╴w  The class `md:w-[158px]` can be written as `md:w-39.5`  (suggestCanonicalClasses) [58, 239]
     ├╴i  'typeX' is declared but never used. typescript (6196) [3, 6]
     └╴i  'unusabled_variable' is declared but its value is never read. typescript (6133) [6, 9]
```

### Code Actions

Type hovering on line 3 should show `"hi" | "bye"`.

Code actions in this line should show:

```text
 1. Disable @typescript-eslint/no-unused-vars for this line [eslint]
 2. Disable @typescript-eslint/no-unused-vars for the entire file [eslint]
 3. Show documentation for @typescript-eslint/no-unused-vars [eslint]
 4. Remove unused declaration for: 'typeX' [ts_ls]
 5. Delete all unused declarations [ts_ls]
 6. Move to a new file [ts_ls]
```

---

On line 19, code actions should show:

```text
 1. Delete 'gap-6' [tailwindcss]
 2. Delete 'gap-6' [tailwindcss]
 3. Move to a new file [ts_ls]
 4. Extract to inner function in function 'Home' [ts_ls]
 5. Extract to function in module scope [ts_ls]
 6. Extract to constant in enclosing scope [ts_ls]
 7. Extract to constant in module scope [ts_ls]
```

### Completions

You should be able to complete:

---

A line after the type.

```text
console.
```

into:

```text
log
dir
info
time
...
```

---

Inside any className tag.

```text
<div className="flex-">content</div>
```

into:

```text
flex-col
flex-1
flex-2
...
```

## Running it

You don't need to, this is for editor bug hunting, but if you want to:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see
the result.

You can start editing the page by modifying `app/page.tsx`. The page
auto-updates as you edit the file.
