# vscode-markdown-link-test
VSCode1.60で導入された[markdownファイルの相対パスリンク対応](https://code.visualstudio.com/updates/v1_60?WT.mc_id=devcloud-00000-cxa#_links-between-markdown-cells)の動作テスト
1. 今開いているパスからの相対パス指定すると[そのmarkdownファイルに移動できる](SubDirectory/SubFile.md)
    - 区切り文字
        - GitLab/GitHub：[/](SubDirectory/SubFile.md)🔵、[\\ ](SubDirectory\SubFile.md)✖
        - VSCode：[/](SubDirectory/SubFile.md)🔵、[\\ ](SubDirectory\SubFile.md)🔵
    - GitHub/GitLab：ファイルの先頭
    - VSCode：前回閉じた時のカーソル位置で開く(どの程度キャッシュが残るかは不明)
2. [ファイルの拡張子を外した場合](SubDirectory/SubFile)
    - GitHub/GitLab：エラー
    - VSCode：エラーは出るけど開ける
3. パスは相対パスのみ可[絶対パスは開けない](C:/Users/repos/vscode-markdown-link-test/SubDirectory/SubFile.md)
4. [レベル1](SubDirectory/SubFile.md#レベル1)
5. [レベル2](SubDirectory/SubFile.md#レベル2)
6. [レベル3](SubDirectory/SubFile.md#レベル3)
7. [レベル4](SubDirectory/SubFile.md#レベル4)
8. [レベル5](SubDirectory/SubFile.md#レベル5)
9.  [レベル6](SubDirectory/SubFile.md#レベル6)
10. [#を複数個入れた場合](SubDirectory/SubFile.md######レベル1)
    - GitHub/VSCode：開ける
    - GitLab：開くページによって開けたり開けなかったり(トップページ✖、ファイルページ🔵)
11. 複数ある場合は[最初のモノが選ばれる](SubDirectory/SubFile.md#同じ名前の項目)
12. [日本語やEmojiが含まれるパスも可能](サブディレクトリ/😀.md#🥴)
