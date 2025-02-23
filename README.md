2025年の横浜F・マリノス試合スケジュールのicsファイルを作成するpythonスクリプトです。

### スケジュールをChatGPT等で取得する

（例）ChatGPT o3-mini-high へのプロンプト

```
下記URLに記載の横浜F・マリノス(横浜FM)の試合日程に基づき、1つの表を作成して（サンプルではなく全日程を含めること）。形式はJSONとして。
2025年の全日程を含み、JリークだけでなくACチャンピオンズリーグエリート日程も含めて。

- 日付（yyyy/mm/dd形式）
- 時刻（hh/mm形式）
- 対戦チーム名
- スタジアム
- 補足事項（日程に関する注意事項など）

https://www.jleague.jp/match/search/?category%5B%5D=j1&category%5B%5D=leaguecup&category%5B%5D=j2&category%5B%5D=j3&category%5B%5D=playoff&category%5B%5D=j2playoff&category%5B%5D=J3jflplayoff&category%5B%5D=emperor&category%5B%5D=acle&category%5B%5D=acl2&category%5B%5D=acl&category%5B%5D=fcwc&category%5B%5D=supercup&category%5B%5D=asiachallenge&category%5B%5D=jwc&club%5B%5D=yokohamafm&year=2025&month%5B%5D=01&month%5B%5D=02&month%5B%5D=03&month%5B%5D=04&month%5B%5D=05&month%5B%5D=06&month%5B%5D=07&month%5B%5D=08&month%5B%5D=09&month%5B%5D=10&month%5B%5D=11&month%5B%5D=12&tba=1
```

### 取得したJSONテキストをもとに、fmarinos2025.py を修正する

```python
def get_schedule():
    return [
        {
            "日付": "2025/02/12",
            "時刻": "19:02",
            "対戦チーム名": "上海申花",
            "スタジアム": "横浜国",
            "補足事項": "AFCチャンピオンズリーグエリート リーグステージ MD7"
        },
        {
            "日付": "2025/02/15",
            "時刻": "14:03",
            "対戦チーム名": "新潟",
            "スタジアム": "日産スタジアム",
            "補足事項": "明治安田J1リーグ 第1節"
        },
        {
        （以下略）
```

### fmarinos2025.py を実行する（fmarinos2025.icsが作成される）

詳しくは書かない。

* あらかじめvenv（仮想環境）の作成・有効化や、パッケージのインストールを必要に応じ実施しておくこと。
* `fmarinos2025.ics` をGoogleカレンダー等にインポートする。

### 注意事項

* 時刻未定の場合は icsファイル上、終日スケジュールとしている。
* スケジュールは変更となる場合があるので、適時再設定すること（カレンダーの再作成が必要かも）。
