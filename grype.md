# about
dockerコンテナの中身をスキャンして、脆弱性がないか確認するツール

# manual
1．[ここ](https://github.com/anchore/grype/releases)を参照して最新のパッケージを確認する。
※リリース直近すぎて不安なら1つ前とかにしておく

2.対応したパッケージのURLをコピーしておく
今回は以下
> https://github.com/anchore/grype/releases/download/v0.108.0/grype_0.108.0_linux_amd64.tar.gz

3.tmpディレクトリを作成して移動
> mkdir /tmp/grype/ && cd /tmp/grype/ && pwd
> > /tmp/grype/が返ってくること

4. wgetでパッケージを取得
> wget https://github.com/anchore/grype/releases/download/v0.108.0/grype_0.108.0_linux_amd64.tar.gz | ls -l
> > パッケージがダウンロードできていること

5.tarでパッケージ展開
> tar xvf grype_0.108.0_linux_amd64.tar.gz | ls -l
> > grypeがあること

6.パスが通ったとこに移動させる
> mv grype /usr/local/bin/ | ls -l /usr/local/bin/grype
> >あること

7.コマンドが使えるか確認
> grype version
> >バージョン確認できたこと

# HOWTO
1.Dockerイメージ一覧を確認
> docker images
> > 確認したいイメージ名を取得しておく

2.イメージを確認する
> grype [イメージ名] --scope all-layers
> > なんかいろいろ出るから確認する

