## Start a new project
```sh
npm create svelte@latest <project_name>
cd <project_name>
npm install
npm run dev
```


```yaml
theme:
  features:
    - content.code.annotate # (1)
```

1.  :man_raising_hand: I'm a code annotation! I can contain `code`, __formatted
    text__, images, ... basically anything that can be written in Markdown.



```rs title="test.rs" 
--8<--
code/test.rs
--8<--
```
