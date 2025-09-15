# nextBTC Inscription Toolkit | nextBTC 铭文工具套件

Welcome to the nextBTC Inscription Toolkit, a suite of decentralized applications for publishing and reading content on the nextBTC blockchain. This project follows the "layered" Bitcoin philosophy, providing powerful on-chain content capabilities without burdening the main chain.

The toolkit consists of two core components:
*   **CodeScribe**: The "pen" for writing inscriptions.
*   **NPIP Inscription Explorer**: The "magnifying glass" for reading them.

Both tools are designed to be completely sovereign, connecting directly to your personal nextBTC full node. This ensures a secure, private, and censorship-resistant experience.

---

欢迎来到 nextBTC 铭文工具套件。这是一套用于在 nextBTC 区块链上发布和读取内容的去中心化应用程序。本项目遵循“分层”的比特币哲学，旨在提供强大的链上内容发布功能，同时不增加主链的负担。

本套件包含两个核心组件：
*   **CodeScribe**: 用于写入铭文的“笔”。
*   **NPIP Inscription Explorer**: 用于读取铭文的“放大镜”。

两个工具都被设计为完全主权化，直接连接到您个人的 nextBTC 全节点，确保了整个体验的安全性、私密性和抗审查性。

---

## Core Components |核心组件

### 1. CodeScribe (The Inscriber) | CodeScribe (铭刻工具)

CodeScribe is a powerful desktop tool that allows you to "inscribe" data onto the nextBTC blockchain. It's your gateway to creating permanent, immutable on-chain records.

**Features:**
*   **Versatile Input**: Inscribe any text or even convert images into detailed ASCII art.
*   **Intelligent Wallet Management**: Automatically scans all loaded wallets to find one with sufficient funds (UTXOs) for the transaction fees.
*   **Automatic Fan-Out**: If a wallet has enough balance but lacks small UTXOs, it intelligently creates a "fan-out" transaction to prepare the funds, prompting you to wait for one confirmation.
*   **Transparent Cost Estimation**: Before any transaction is sent, it provides a clear cost estimate for the entire inscription process.
*   **Real-Time Logging**: Monitor the entire inscription process through a detailed on-screen log.

---

CodeScribe 是一个功能强大的桌面工具，能让您将任意数据“铭刻”到 nextBTC 区块链上。它是您创建永久、不可篡改的链上记录的入口。

**功能特性：**
*   **多样化输入**: 支持铭刻任意文本，甚至可以将图片转换为精细的字符画。
*   **智能钱包管理**: 自动扫描所有已加载的钱包，寻找一个拥有足够“零钱”（UTXO）的钱包来支付手续费。
*   **自动扇出**: 如果钱包总余额充足但缺少“零钱”，程序会智能地发起一笔“扇出”交易来准备资金，并提示您等待一个区块确认后再试。
*   **透明的成本预估**: 在发送任何交易之前，程序会提供一个关于整个铭刻流程的总成本预估。
*   **实时日志**: 通过屏幕上的详细日志，可以监控整个铭刻过程。

### 2. NPIP Inscription Explorer (The Reader) | NPIP 铭文浏览器 (读取工具)

The NPIP Inscription Explorer allows anyone to read and verify inscriptions directly from the blockchain. Using a unique "Inscription Locator," you can retrieve any content inscribed with CodeScribe or a compatible tool.

**Features:**
*   **Truly Decentralized**: Connects directly to your own node. No third-party APIs or servers.
*   **Local-First Indexing**: Scans the blockchain and builds a local database for fast and private queries.
*   **Simple Retrieval**: Just paste the `block_height:txid` locator to find and display the full content.
*   **Real-Time Syncing**: Automatically watches for new blocks to keep its index up-to-date.

---

NPIP 铭文浏览器允许任何人直接从区块链上读取和验证铭文。使用独一无二的“铭文定位信息”，您可以找回任何由 CodeScribe 或兼容工具铭刻的内容。

**功能特性：**
*   **真正去中心化**: 直接连接到您自己的节点，不依赖任何第三方 API 或服务器。
*   **本地优先索引**: 扫描区块链并在本地建立数据库，实现快速、私密的查询。
*   **轻松读取**: 只需粘贴 `区块高度:交易ID` 格式的定位信息，即可查找并显示完整内容。
*   **实时同步**: 自动监测新区块，并保持索引实时更新。

## Prerequisites (For Both Tools) | 先决条件 (两个工具通用)

Before using either tool, please ensure your environment meets all the following conditions:

在使用任一工具前，请确保您的计算机环境已满足以下全部条件：

1.  **Run nextBTC Core Node**: You must have the nextBTC Core full node installed and running. Ensure it is fully synchronized with the network.

    **运行 nextBTC 核心节点**: 您必须已经安装并运行了 nextBTC 核心全节点，并确保它已完全同步了区块链数据。

2.  **Configure `bitcoin.conf`**: In your nextBTC data directory, ensure your `bitcoin.conf` file contains the following lines (uncommented):

    **正确配置 `bitcoin.conf` 文件**: 在您的 nextBTC 数据目录中，找到 `bitcoin.conf` 文件，并确保文件中至少包含以下内容 (并且没有被 `#` 注释)：
    ```ini
    server=1
    txindex=1
    rpcuser=your_rpc_username
    rpcpassword=your_strong_rpc_password
    ```
    *   **Recommendation**: For best results with CodeScribe, also set a default transaction fee: `settxfee=0.0001`
    *   **重要提示**: 如果您是首次添加 `txindex=1`，您必须使用 `-reindex` 标志重新启动您的 nextBTC 核心节点。

3.  **Wallet Ready**: Your node must have at least one wallet created and loaded, with sufficient nextBTC to cover transaction fees.

    **钱包准备**: 您的 nextBTC 节点必须至少创建并加载了一个钱包，并确保钱包里有足够的 nextBTC 用于支付手续费。

## Installation & Setup | 安装与设置

1.  **Download**: Download the latest releases of `CodeScribe.exe` and `NPIP-INSEXP.exe` from the [Releases](https://github.com/your-username/your-repo/releases) page.

    **下载**: 从本项目的 [Releases](https://github.com/your-username/your-repo/releases) 页面下载 `CodeScribe.exe` 和 `NPIP-INSEXP.exe` 的最新版本。

2.  **Initial Setup (CodeScribe)**: The first time you run `CodeScribe.exe`, a pop-up will ask you to select your "Bitcoin data folder". **You must select the data directory of your nextBTC node** (the folder where `bitcoin.conf` is located). The program will save this path and won't ask again.

    **初始化设置 (CodeScribe)**: 首次运行 `CodeScribe.exe` 时，会弹窗要求您“选择Bitcoin数据文件夹”。**请务必选择您 nextBTC 核心节点的数据目录** (即 `bitcoin.conf` 文件所在的那个目录)。程序会自动保存该路径，之后不再需要此步骤。

3.  **Configure `config.ini` (NPIP Explorer)**: The explorer uses a `config.ini` file. Make sure the `[RPC]` section in this file exactly matches the credentials in your `bitcoin.conf`.

    **配置 `config.ini` (NPIP 浏览器)**: 浏览器使用一个 `config.ini` 文件。请确保文件中的 `[RPC]` 部分与您 `bitcoin.conf` 中的凭据完全一致。

## Usage | 使用方法

### Writing with CodeScribe | 使用 CodeScribe 写入

1.  **Create Content**: In the "✍️ Inscribe Text" tab, either paste your text or use the "Load Image" and "Generate ASCII Art" buttons to create your content.

    **创建内容**: 在“✍️ 铭刻文本”选项卡下，可以直接粘贴文本，或使用 [① 载入图片] 和 [② 生成字符画] 按钮来创建您的内容。

2.  **Start Inscription**: Click the **[Start Inscription Flow]** button. Review the cost estimate and click "Yes" to proceed.

    **开始铭刻**: 点击 **[开始铭刻流程]** 按钮。仔细阅读弹出的成本预估对话框，然后点击“是”继续。

3.  **Unlock Wallet**: If your wallet is encrypted, make sure it is unlocked in the nextBTC-Qt client.

    **解锁钱包**: 如果您的钱包已加密，请确保在 nextBTC-Qt 客户端中解锁它。

4.  **Save the Locator**: The tool will automatically handle the transactions. Once finished, the log will display a critical piece of information: the **Inscription Locator**.

    **保存定位信息**: 工具会自动处理所有交易。完成后，日志区会显示一条最重要的信息：**铭文定位信息**。
    ```
    [block_height:a_long_64_character_transaction_id]
    Example: 76469:b83a042e26d14e32bf48da92afa1f4ebb5d57eaf3258dea67e0ec9674cee1e04
    ```
    **Copy and save this locator! It is the only key to retrieving your inscription.**

    **请务必复制并安全保存这个定位信息！这是未来找回这篇铭文的唯一凭证。**

### Reading with NPIP Explorer | 使用 NPIP 浏览器读取

1.  **Launch**: Run `NPIP-INSEXP.exe`. A terminal window will open to show sync progress, and the UI will open in your default browser.

    **启动**: 运行 `NPIP-INSEXP.exe`。一个终端窗口会显示同步进度，同时程序会在您的默认浏览器中打开用户界面。

2.  **Enter Locator**: In the explorer's web interface, paste the full `block_height:txid` locator into the input box.

    **输入定位信息**: 在浏览器的网页界面中，将完整的“区块高度:TXID”信息粘贴到输入框。

3.  **Read Content**: Click the "Find and Read" button. The explorer will retrieve, reassemble, and decompress the data, displaying the original content.

    **读取内容**: 点击 [查找并读取] 按钮。浏览器会自动从链上还原出完整的铭文内容。

---

**Public Web Explorer**: You can also use the official public web explorer to view any known inscription:
<br>**公共网页浏览器**: 您也可以使用官网的公共浏览器来查看任何已知的铭文：
[https://nextbtc.rf.gd/inscriptionv2.html](https://nextbtc.rf.gd/inscriptionv2.html)

## Author | 作者

*   **达哥 (@Btcdage)**

Now you are fully equipped to participate in the decentralized world of on-chain data. Start by inscribing your first message!

现在，您已经完全掌握了这套工具。去中心化的世界，从记录您的第一条链上铭文开始！
