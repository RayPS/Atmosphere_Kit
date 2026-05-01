# Atmosphere_Kit — 大气层整合包生成脚本

## 功能如下：

- 下载最新：
  - 大气层核心
    - [x] `Atmosphere + Fusee` [From Here](https://github.com/Atmosphere-NX/Atmosphere/releases/latest)
    - [x] `Hekate + Nyx 简体中文` [From Here](https://github.com/easyworld/hekate/releases/latest)
  - Payload 插件
    - [x] 主机系统的密钥提取工具 `Lockpick_RCM` [From Here](https://github.com/Kofysh/Lockpick_RCM/releases/latest)
    - [x] Hekate 下的文件管理工具 `TegraExplorer` [From Here](https://github.com/suchmememanyskill/TegraExplorer/releases/latest)
  - Nro 插件
    - [x] 联网检测是否屏蔽任天堂服务器 `Switch_90DNS_tester` [From Here](https://github.com/meganukebmp/Switch_90DNS_tester/releases/latest)
    - [x] 游戏安装、存档管理和文件传输工具 `DBI` [From Here](https://github.com/rashevskyv/dbi/releases/latest)
    - [x] Homebrew 启动器 / 文件管理 `Sphaira` [From Here](https://github.com/ITotalJustice/sphaira/releases/latest)
    - [x] 系统升级工具 `daybreak` （随 Atmosphere 官方包内置）
  - Ultrahand Overlay 框架
    - [x] 加载器 `nx-ovlloader` [From Here](https://github.com/WerWolv/nx-ovlloader/releases/latest)
    - [x] 菜单 `Ultrahand-Overlay` [From Here](https://github.com/ppkantorski/Ultrahand-Overlay/releases/latest)
  - Ovl 插件
    - [x] 金手指工具 `EdiZon` [From Here](https://github.com/proferabg/EdiZon-Overlay/releases/latest)
    - [x] 系统模块管理 `ovl-sysmodules` [From Here](https://github.com/WerWolv/ovl-sysmodules/releases/latest)
    - [x] 系统监视 `StatusMonitor` [From Here](https://github.com/masagrator/Status-Monitor-Overlay/releases/latest)
    - [x] 掌机底座模式切换 `ReverseNX-RT` [From Here](https://github.com/masagrator/ReverseNX-RT/releases/latest)
    - [x] 局域网联机 `ldn_mitm` [From Here](https://github.com/spacemeowx2/ldn_mitm/releases/latest)
    - [x] 虚拟 Amiibo `emuiibo` [From Here](https://github.com/XorTroll/emuiibo/releases/latest)
    - [x] 时间同步 `QuickNTP` [From Here](https://github.com/nedex/QuickNTP/releases/latest)
    - [x] 色彩调整 `Fizeau` [From Here](https://github.com/averne/Fizeau/releases/latest)
    - [x] 系统签名补丁 `sys-patch` [From Here](https://github.com/impeeza/sys-patch/releases/latest)
    - [x] 超频插件 `sys-clk` [From Here](https://github.com/retronx-team/sys-clk/releases/latest)
  - 其他
    - [x] 蓝牙手柄插件 `MissionControl` [From Here](https://github.com/ndeadly/MissionControl/releases/latest)

- 文件操作：
    - [x] 移动 `fusee.bin` 至 `bootloader/payloads` 文件夹
    - [x] 将 `hekate_ctcaer_*.bin` 重命名为 `payload.bin`
    - [x] 在 `bootloader` 文件夹中创建 `hekate_ipl.ini`
    - [x] 在根目录中创建 `exosphere.ini`
    - [x] 在 `atmosphere/hosts` 文件夹中创建 `emummc.txt` 和 `sysmmc.txt`
    - [x] 在根目录中创建 `boot.ini`
    - [x] 在 `atmosphere/config` 文件夹中创建 `override_config.ini`
    - [x] 在 `atmosphere/config` 文件夹中创建 `system_settings.ini`
    - [x] 删除 `switch` 文件夹中 `haze.nro`
    - [x] 删除 `switch` 文件夹中 `reboot_to_payload.nro`

## 使用说明（仅适用于 `Linux`，科学上网环境）:
  - 安装 `jq` 工具
  - 运行脚本（switchScript.sh）
  - 可选：自建 90DNS conntest 服务器后用 `MY_90DNS_IP=<你的IP> ./atmosphere_kit.sh` 覆盖默认 `127.0.0.1`

## 关于 90DNS（强烈建议自建）

CFW 模式下 Atmosphere 通过 `atmosphere/hosts/` 把任天堂域名劫持到本地黑洞，避免遥测/上报。

- 默认 `127.0.0.1`：纯黑洞，conntest 失败，**最安全**，对存档导出等离线用途无影响。
- 公共 90DNS（如 `95.216.149.205`）：第三方个人维护，**不推荐**，你的设备指纹会出现在陌生服务器日志里，且偶有宕机。
- **自建 nginx 90DNS**：本仓库根目录提供 `90dns.conf`，参考其中部署说明在自己 VPS / 家庭路由器上跑一个，安全可控。

仓库 CI 使用作者自建的 conntest 服务器，fork 自用请改为你自己的 IP 或保持默认 `127.0.0.1`。

## GitHub Actions 所需 Secrets
| Secret | 说明 |
|--------|------|
| `TOKEN` | 具有 `repo` 权限的 GitHub Personal Access Token（PAT），用于创建 Release 和清理旧 Workflow Run |

## 致谢

本项目基于以下上游项目的思路和代码发展而来，感谢原作者们的贡献：

| 项目 | 地址 |
|------|------|
| huangqian8/SwitchScript（主要上游） | https://github.com/huangqian8/SwitchScript |
| Fraxalotl（原始脚本作者） | https://rentry.org/CFWGuides |

## 参考资料

| 资料 | 地址 |
|------|------|
| Switchbrew Title List（Switch 官方及 Homebrew Title ID 总表） | https://switchbrew.org/wiki/Title_list |

## 更新日志
- 2026-05-02 自建 90DNS conntest 服务器；hosts 模板换成 nh-server 权威列表 + `MY_90DNS_IP` 变量驱动；移除 OC_Toolkit；sysMMC 补全遥测屏蔽；`DEBUG=1` 时屏蔽 `GITHUB_TOKEN` 泄露
- 2026-05-01 精简工具列表，替换所有非官方 fork 为官方源；删除 Sigpatches（改用 sys-patch）
- 2026-04-18 添加 `Sphaira` 启动器
- 2026-03-01 精简优化 `switchScript.sh`
- 2025-12-28 去除 `Zing` 和 `sys-tune`，更新 `DBI`、`Awoo Installer` 及 `emuiibo` 仓库地址
