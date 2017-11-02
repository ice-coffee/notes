##RecyclerView

###加载不同的显示方式
1. listview效果
```
setLayoutManager(new LinearLayoutManager(context));
```
2. gridview效果
```
setLayoutManager(new GridLayoutManager(context));
```
3. 瀑布流效果
```
setLayoutManager(new StaggeredGridLayoutManager(context));
```
4. 横向listview
```
LinearLayoutManager linearLayoutManager = new LinearLayoutManager(context);
linearLayoutManager.setOrientation(RecyclerView.HORIZONTAL);
setLayoutManager(linearLayoutManager);
```

###禁止滑动

```
LinearLayoutManager linearLayoutManager = new LinearLayoutManager(context)
{
    @Override
    public boolean canScrollVertically()
    {
        return false;
    }
};
setLayoutManager(linearLayoutManager);
```