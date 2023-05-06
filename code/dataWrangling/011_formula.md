# Formula

---

```R
as.formula( paste0("hp~disp+gear") )
# equals to 
reformulate( c("disp", "gear"), "hp" )
```