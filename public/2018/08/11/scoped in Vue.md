## If you want to use `scoped` in .vue file and you import a third party component such as ElementUI and you wanna modify the style of it

## This is what you need to do:

```
<style lang="less" scoped>

.banner /deep/ .el-button {
  ...
}
</style>
```

## use `/deep/` to penetrate the `scoped`, you may see someone using `>>>` to achieve the same goal. 
### However, if you are using `less`, you are not able to use this directly. You will need to use it this way  `~">>>"`, which is not what I like to do
