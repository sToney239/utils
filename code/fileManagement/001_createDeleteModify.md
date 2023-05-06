# File managent

---

## Basic 

- `fs::dir_create()`
- ``fs::file_move()` also can rename the file
- `fs::file_copy()`
- `fs::file_delete()`
- `fs::dir_info()`

## List folder files

```R
here::here("climate") %>%
  fs::dir_ls() %>%
  base::basename()
```

## read multiple file in a list to seperate

 `base::list2env()` 

## Change Modified Date

```R
# exact_date <- as.POSIXlt("2017-03-11 12:03:42")
Sys.setFileTime(file_path, exact_date)
```

