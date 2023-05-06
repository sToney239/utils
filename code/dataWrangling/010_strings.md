# Strings

---

## combining strings

```R
vctrs::vec_paste0("My name is ", name, ".") # fastest
glue::glue("My name is {name}.") # safe choice
paste0("My name is ", name, ".") # slowest
```

## remove spaces

```R
str_trim()
str_squish()
```

## compress strings

```R
paste( c("apple", "peach", "banana"), collapse = "," )
toString(c("apple", "peach", "banana"))
```