# Online Learning

## Elementary English Vocabulary Learning

This is an interactive web application for learning elementary English vocabulary. It displays one word at a time in a flashcard format and includes various interactive features.

### Features

1. **Flashcard Interface**
   - Front side shows the word
   - Back side shows meaning and example sentence
   - Click or use keyboard to flip cards

2. **Navigation Options**
   - Navigate through words (previous, next)
   - View random words
   - Track progress with a visual progress bar

3. **Interactive Elements**
   - Text-to-speech pronunciation
   - Youdao Dictionary integration
   - Keyboard shortcuts for quick navigation
   - Customizable settings

4. **Animations and Transitions**
   - Smooth card flipping animations
   - Transition effects between words
   - Interactive UI elements

### How to Use

1. Open `english_vocabulary.html` in your web browser
2. Use the navigation buttons or keyboard shortcuts to move through the vocabulary list:
   - Left/Right arrows: Previous/Next word
   - Space: Flip card
   - R: Random word
   - S: Speak the current word
3. Click on the card to flip between the word and its meaning
4. Click on "Look up in Youdao Dictionary" to see more detailed information
5. Use the settings panel (gear icon) to customize your experience

### Settings Options

- **Auto-pronunciation**: Choose when words are automatically pronounced
- **Card flip behavior**: Set cards to flip automatically or manually
- **Speech rate**: Adjust the speed of pronunciation

### Data

The vocabulary words are stored in `data/elementary_english.json`. You can modify this file to add or remove words as needed. Word meanings and example sentences are included directly in the application.

## 新功能：百度汉语API集成

我们现在支持从百度汉语自动获取汉字的拼音、释义和例句。这个功能需要启动本地服务器来处理API请求。

### 如何启动服务器

1. 确保你已经安装了Node.js（建议使用v14或更高版本）
2. 在项目根目录下运行以下命令安装依赖：
   ```
   npm install
   ```
3. 启动服务器：
   ```
   npm start
   ```
   或者使用开发模式（自动重启）：
   ```
   npm run dev
   ```
4. 服务器将在 http://localhost:3000 上运行

### 如何使用百度汉语API功能

1. 启动服务器后，打开中文汉字学习页面
2. 在页面顶部找到"本地数据/百度汉语"切换开关
3. 将开关切换到"百度汉语"位置
4. 系统将自动从百度汉语获取当前汉字的拼音、释义和例句
5. 如果获取失败，系统会自动回退到本地数据

### 技术说明

- 服务器使用Express.js框架
- 使用axios进行HTTP请求
- 使用cheerio解析HTML内容
- 使用CORS允许跨域请求

### 注意事项

- 此功能依赖于百度汉语的网页结构，如果百度汉语更改了其网页结构，可能会导致功能失效
- 频繁请求可能会被百度限制，请适度使用
- 本地数据作为备份，确保在API不可用时仍能正常使用

## 中文汉字学习功能

### 特点

1. **卡片式界面**
   - 正面显示汉字和拼音
   - 背面显示释义和例句
   - 点击或使用键盘翻转卡片

2. **导航选项**
   - 浏览汉字（上一个，下一个）
   - 随机查看汉字
   - 通过进度条跟踪学习进度

3. **交互元素**
   - 文字转语音发音
   - 百度汉语词典集成
   - 键盘快捷键
   - 楷书字体显示

### 在线查询功能

我们提供了两种获取汉字拼音和释义的方式：

#### 1. 本地数据（默认）
- 使用预定义的本地数据库
- 包含常用汉字的拼音、释义和例句
- 无需网络连接，速度快

#### 2. 在线查询（通过公共CORS代理）
- 从百度汉语自动获取最新的拼音、释义和例句
- 无需后端服务器，直接在浏览器中运行
- 使用公共CORS代理服务解决跨域问题
- 如果一个代理服务失败，会自动尝试其他代理服务
- 如果所有代理服务都失败，会回退到本地数据

### 如何使用在线查询功能

1. 打开中文汉字学习页面
2. 在页面顶部找到"本地数据/在线查询"切换开关
3. 将开关切换到"在线查询"位置
4. 系统将自动从百度汉语获取当前汉字的拼音、释义和例句
5. 如果获取失败，系统会自动回退到本地数据

### 技术说明

- 使用公共CORS代理服务解决跨域问题
- 使用DOMParser和正则表达式解析HTML内容
- 多重备份机制确保功能可靠性
- 完全在前端实现，无需后端服务器

### 注意事项

- 此功能依赖于百度汉语的网页结构，如果百度汉语更改了其网页结构，可能会导致功能失效
- 公共CORS代理服务可能有使用限制，如果频繁请求可能会被限制
- 本地数据作为备份，确保在API不可用时仍能正常使用
