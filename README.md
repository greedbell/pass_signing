# pass_signing

苹果官方的[developer downloads area](https://developer.apple.com/services-account/download?path=/iOS/Wallet_Support_Materials/WalletCompanionFiles.zip) 中的 `rsign_pass ` 有BUG。会报下面的错误:

```
 /Users/Bell/Documents/Apple/Wallet/WalletCompanionFiles/SamplePasses/Coupon.pass/
/usr/local/lib/ruby/gems/2.2.0/gems/sign_pass-1.0.1/lib/sign_pass.rb:61:in `initialize': wrong number of arguments (4 for 5..6) (ArgumentError)
	from bin/rsign_pass:40:in `new'
	from bin/rsign_pass:40:in `<main>'
```

这是修复后的 `rsign_pass `

## 安装

```shell
$ gem build sign_pass.gemspec
$ gem install sign_pass-1.0.1.gem
```

## 使用

```
rsign_pass -p /path/to/pass/directory -c /path/to/ssl/certificate -w certififcate-password -i wwdr_intermediate_certificate_path -o /path/for/output/file"
```

添加了个 -i 参数，对应`wwdr_intermediate_certificate_path`,从<http://www.apple.com/certificateauthority/AppleWWDRCAG2.cer> 下载
