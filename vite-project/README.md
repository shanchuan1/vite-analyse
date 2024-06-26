# Vue 3 + Vite

在Vite项目中，如果你希望直接以当前工作目录作为根目录启动开发服务器，或者指定一个替代的根目录，实际上并不需要在vite.config.js中进行配置。Vite CLI命令行工具本身就支持这样的功能。

# 直接以当前工作目录启动
通常情况下，如果你的项目结构是标准的Vite项目结构，你只需在项目根目录下运行以下命令：
```js
vite
// # 或者
npm run dev
// # 或者如果你使用Yarn
yarn dev
```
这条命令默认就是以当前目录作为根目录启动开发服务器。

# 指定一个替代的根目录启动
如果你想指定一个子目录作为根目录来启动开发服务器，你可以使用如下命令格式：
``` js
vite serve some/sub/dir
// 这里的some/sub/dir是你项目内的一个子目录路径，Vite将会把该目录视为项目的根目录来启动开发服务器。
```

# 注意事项
确保你指定的子目录中包含Vite所需的文件结构，至少应有一个index.html作为入口，并且如果有相关的资源引用，路径也需要根据新的根目录进行调整。
这种方式不会改变vite.config.js中的配置，仅仅是在启动时临时改变了服务的根目录。如果你需要永久更改项目的根目录，应该直接在vite.config.js中的root选项中指定。
# 修改配置文件根目录
如果你确实需要在配置文件中修改根目录（尽管这通常不是为了临时指定一个子目录的目的），可以在vite.config.js中这样做：
```js
import { defineConfig } from 'vite';

export default defineConfig({
  root: 'path/to/your/custom/root', // 替换为你的自定义根目录路径
  // ... 其他配置
});
```
但是，请记住，这种方式是永久性的改变项目根目录，而非临时指定启动时的根目录。