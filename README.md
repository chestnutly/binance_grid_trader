#  网格交易策略

## 使用 how to use
1. 修改配置文件, config your config file.

```json
{
  "platform": "binance_spot",  
  "symbol": "BTCUSDT",
  "api_key": "replace your api key here",
  "api_secret": "replace your api secret here",
  "gap_percent": 0.001,
  "quantity": 0.001,
  "min_price": 0.01,
  "min_qty": 0.001,
  "max_orders": 1,
  "proxy_host": "127.0.0.1",
  "proxy_port": 1087
}

```

1. platform 是交易的平台, 填写 binance_spot 或者 binance_future,
   如果交易的是合约的，就填写binance_future.
2. symbol 交易对: BTCUSDT, BNBUSDT等
3. api_key : 从交易所获取
4. api_secret: 交易所获取
5. gap_percent: 网格交易的价格间隙
6. quantity : 每次下单的数量
7. min_price: 价格波动的最小单位, 用来计算价格精度： 如BTCUSDT 是0.01,
   BNBUSDT是0.0001, ETHUSDT 是0.01, 这个价格要从交易所查看，每个交易对不一样。
   
8. min_qty: 最小的下单量, 现货B要求最小下单是10USDT等值的币, 而对于合约来说,
   BTCUSDT要求是0.001个BTC
9. max_orders: 单边的下单量
10. proxy_host: 如果需要用代理的话，请填写你的代理 your proxy host, if you
    want proxy
11. proxy_port: 代理端口号 your proxy port for connecting to binance.


修改完配置文件后，用shell 命令运行下面的shell 命令:
> sh start.sh 



## 网格交易策略使用行情
- 震荡行情
- 适合高波动率的品种
- 适合现货， 如果交易合约，需要注意防止极端行情爆仓。



## linux 常用命令

- cd  # 是切换工作目录， 具体使用可以通过man 指令 | 指令 --help
- clear
- ls  # 列出当前文件夹的文件
- rm 文件名  # 删除文件
- rm -rf 文件夹 # 删除文件
- cp # 拷贝文件 copy 
- scp scp binance_grid_trader.zip ubuntu@xxx.xxx.xxx.xxx:/home/ubuntu
- pwd 
- mv  #  移动或者剪切文件
- ps -ef | grep main.py    # 查看进程
- kill 进程id  # 杀死当前进程





