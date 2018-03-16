##Shell


###文本搜索
 - 搜索指定文件中指定文本：
```
egrep 'keyword1|keyword2'   /path/*/config.xml
```

###文本替换
 - 逐行替换
 
 ```
#!/bin/bash
while IFS='' read -r f || [[ -n "$f" ]]; do
    echo "Text read from file: $f"
    sed -e 's/oldkeyword1/newkeyword1/g' -e 's/oldkeyword2/newkeyword2/g' "$f" > "$f.ok"
    diff "$f.ok" $f

    rm $f
    mv "$f.ok" $f
done < "$1"
```


##Python
###数据处理
 - 列表内容去重
 
```
pathlist = []
pathlist.append(data)
pathlist = list(set(pathlist))
print pathlist
```


###文件处理
 - 判断是否是文件
 
```
import os
os.path.isfile(file)
```

 - 写文件
 
```
t=open(file,"w")
for x in pathlist:
    t.write(x + '\n')
    pass
t.close
```

###第三方调用
 - 执行shell 命令
 
 ```
 import subprocess
 subprocess.call(["./replace.sh", ptargetFile])
 ```