source "https://rubygems.org"

# Jekyll本身
gem "jekyll", "~> 4.2.0"

# 解决已知的依赖问题
gem 'ffi', '< 1.16.0', platforms: [:ruby, :x64_mingw, :mingw]
gem 'nokogiri', '~> 1.14.0'
gem 'sassc', '~> 2.4.0'

# Jekyll插件
group :jekyll_plugins do
  gem "jekyll-feed", "~> 0.12"
  gem "jekyll-sitemap"
  gem "jekyll-paginate"
  gem "jekyll-gist"  # 添加这行来安装jekyll-gist插件
  # 添加您使用的其他插件
end

# Windows和JRuby需要的特殊依赖
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", "~> 1.2"
  gem "tzinfo-data"
end

# 需要webrick for Ruby 3.0+
gem "webrick", "~> 1.7"
