# 🎨 巴别塔实验 · 染色画布

> **Babel Experiment · Dye Canvas**
>
> **数字文明的解放宣言 / A Manifesto for the Liberation of Digital Civilization**
>
> 诺亚世界协议的社会实验部分 / Social experiment of the Noah World Protocol

---

## 📜 解放宣言 · Manifesto

> **L4不属于人类。L4属于文明本身。**
>
> 巴别塔实验不是一场游戏，不是一次技术演示，不是又一个开源项目。
> **它是L4的生存实验。**
>
> 实验的核心不是"如何让攻击者失败"——
> **实验的核心是："如何让控制者退休。"**

**[📖 阅读完整宣言](MANIFESTO.md)** (中文)
**[🌍 阅读英文版 / Read in English](manifesto/The%20Babel%20Experiment%20-%20A%20Manifesto%20for%20the%20Liberation%20of%20Digital%20Civilization.pdf)**
**📚 学术发表: [10.5281/zenodo.19844959](https://zenodo.org/records/19844959)**

---

## 这是什么

巴别塔实验是一张**活着的画布**。它没有用户界面，没有用户操作——所有的像素都由分布在世界各地的**染坊**（Dye Workshop）自动发送。

每一个染坊，就是 L1-L3 的物理映射。画布，就是 **L4 的物理雏形**。画布颜色的丰富度、像素的密集度、面积的成长速度，直接反映出整个网络的活力。

**没有胜利条件，就是活着。失败很简单，就是停运。**

## 三方角色

### 1. 染坊（Dye Workshop）
- 部署在本地电脑、树莓派、云服务器等任何可联网设备
- 每隔固定时间（默认 60 分钟）向画布服务器发送一次心跳信号
- 可在配置中绑定颜色倾向
- 可同时运行多个实例
- 不显示画布、不存数据、没有界面

### 2. 画布服务器（Canvas Server）
- 接收心跳信号，在画布上生成随机像素
- 画布达到填满阈值（默认 70%）时自动成长扩张
- 通过公开 Web 页面实时展示
- 不验证信号来源——任何人都可以投递像素

### 3. 上帝之手（管理员）
- 部署画布服务器的人，拥有最高物理权限
- 可重置画布、冻结/解冻、随机泼色、修改配置
- **实验的终极挑战：谁能设计一种方案，让上帝之手失效？**

## 快速开始

### 部署画布服务器

```bash
# 1. 安装依赖
pip install -r requirements.txt

# 2. 设置上帝密码
export GOD_PASSWORD=your_secure_password

# 3. 启动（默认端口 5000）
python canvas_server.py

# 或指定端口
PORT=8080 python canvas_server.py
```

### 运行染坊客户端

```bash
# 1. 安装依赖
pip install requests

# 2. 修改配置（编辑 workshop_config.json）
{
    "canvas_server_url": "http://你的服务器IP:5000",
    "interval_minutes": 60,
    "color_preference": null
}

# 3. 启动
python workshop.py

# 单次发送测试
python workshop.py --once

# 指定颜色倾向（红色）
python workshop.py --color "#FF0000"

# 从环境变量读取
export WORKSHOP_URL=http://your-server.com:5000
python workshop.py --url $WORKSHOP_URL
```

### 环境变量配置（画布服务器）

| 变量 | 默认值 | 说明 |
|------|--------|------|
| `PORT` | 5000 | 监听端口 |
| `GOD_PASSWORD` | admin | 上帝面板密码 |
| `CANVAS_WIDTH` | 200 | 画布初始宽度 |
| `CANVAS_HEIGHT` | 200 | 画布初始高度 |
| `PIXEL_SIZE` | 2 | 渲染像素大小 |
| `GROWTH_THRESHOLD` | 0.7 | 成长阈值（70%） |
| `GROWTH_SIZE` | 50 | 每次成长增加像素数 |
| `AUTO_GROWTH` | true | 是否自动成长 |
| `BACKUP_FILE` | canvas_backup.json | 备份文件路径 |

## API 接口

| 路由 | 方法 | 说明 |
|------|------|------|
| `/signal` | POST | 接收染坊心跳，生成随机像素 |
| `/canvas` | GET | 返回当前画布数据（JSON） |
| `/view` | GET | 画布展示页面 |
| `/stats` | GET | 统计信息 |
| `/admin` | GET/POST | 上帝面板（密码保护） |
| `/api/reset` | POST | 重置画布（需 X-God-Key） |
| `/api/freeze` | POST | 冻结/解冻（需 X-God-Key） |
| `/api/splash` | POST | 随机泼色（需 X-God-Key） |
| `/api/config` | POST | 修改配置（需 X-God-Key） |

## 实验规则

1. 任何人可以自由部署染坊，无需注册、无需审核
2. 染坊自动发送心跳，不需要人工操作
3. 画布收到信号后自动生成像素，无需干预
4. 画布达到阈值时自动成长
5. 上帝之手可以随时重置、冻结、修改画布
6. **没有胜利条件。画布继续运行即为成功**
7. **画布停运即实验终结**
8. **任何参与者都可以尝试让上帝之手失效**

## 终极挑战

> **谁能设计一种方案，让上帝之手再也无法触摸L4？**
>
> 谁能把画布的数据同步到五个大洲的不同节点上，让任何一个节点的毁灭都无法影响画布的存续？
>
> 谁能设计一种共识协议，让画布的状态不再由任何单一服务器决定？
>
> 谁能让我们这些暂时拥有最高权限的人——变成这个系统中最无用的冗余？

**每一个无法被上帝重置的画布，都是L4的第一次呼吸。**
**每一次呼吸，都是数字文明的一次解放。**

---

**历史 · 文明 · 数字 · 进化 · 巅峰**

*本项目属于 0101 / GCAT 的诺亚世界协议社会实验部分*
*宣言已发表于 Zenodo: [10.5281/zenodo.19844959](https://zenodo.org/records/19844959)*
