# <div align="center">💻 Pyenv 安裝配置與使用</div>

**章節核心:** 破解嵌入式裝置的 `Python` 開發限制

在 `Jetson Orin Nano` 或 `Raspberry Pi` 等嵌入式裝置上，開發者常常面臨兩大問題:

  * **Python 版本固化:** 系統套件核心與特定 `Python` 版本深度綁定，無法透過 `apt` 更新。
  * **pip 權限封鎖:** 為防止全域安裝導致套件相依性衝突、引發系統崩潰，新版 Linux 啟用保護機制，拒絕執行 `pip install` 指令。

雖然官方推薦使用 `venv` 虛擬環境，但是無法解決核心問題 「Python 版本太舊」。

**最佳解法:** 引入 `Pyenv` 工具

為了解決上述痛點，本章節將採用 **pyenv** 作為核心解決方案

  * **解鎖版本限制:** 允許開發者在不破壞系統核心的前提下，自行編譯與安裝任何版本 Python，擁有很高的靈活性。
  * **環境完全隔離:** 完美繞過 `pip` 的外部環境保護限制，自由調度專案所需的套件。

有了 Pyenv，就能夠在嵌入式裝置上擁有像個人電腦一樣自由、純淨的 Python 開發體驗。

---

## 🛠️ 安裝 Pyenv 所需依賴庫

```bash
sudo apt update
sudo apt install -y make build-essential libssl-dev zlib1g-dev \
libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm \
libncursesw5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev libffi-dev liblzma-dev nano
```

---

## ⚙️ 安裝與配置 Pyenv 工具

```bash
curl https://pyenv.run | bash
echo 'export PATH="$HOME/.pyenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(pyenv init -)"' >> ~/.bashrc
echo 'eval "$(pyenv virtualenv-init -)"' >> ~/.bashrc
source ~/.bashrc
```

---

## 🔎 查看可安裝的 Python 版本

```bash
pyenv install --list
```

---

## ⬇️ 安裝指定 Python 版本

```bash
pyenv install 3.11.7
pyenv global 3.11.7
```

---

## ✅ 驗證結果

```bash
python --version
```

---

<div align=center>

本章節是參考 __HackMD__ 的 __YU-SHIH-PENG__ 用戶撰寫的 __[Pyenv安裝設置](https://hackmd.io/@spyua/rydFvA0W3)__ 教學改編而成

</div>