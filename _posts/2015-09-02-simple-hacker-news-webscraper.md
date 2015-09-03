---
layout: post
title: "Simple Webscraper for Hacker News"
date: 2015-09-02 23:06:34
author: Nayyir Jutha
summary: Showcasing a simple webscraper of hacker news, using the NokoGiri RubyGem
categories: ruby
thumbnail: ruby_lang
tags:
 - webscraper
 - ruby
 - nokogiri
 - hacker
 - news
---

# HackerNews Webscraper

### Post Class

```ruby
class Post

  attr_accessor :title, :url, :points, :item_id

  def initialize(title, url, points, item_id)
    @title = title
    @url = url
    @points = points
    @item_id = item_id
    @comments = []
  end

  def comments
    @comments
  end

  def add_comment(comment_object)
    @comments << comment_object
  end

end
```
### Comment Class

```ruby
class Comment 

  attr_accessor :user_name, :comment_text 

  def initialize(user_name, comment_text)
    @user_name = user_name
    @comment_text = comment_text
  end

  def to_s
    "User: #{@user_name} Comment: #{@comment_text}"
  end

end
```
### Webscraper

```ruby

@url = ARGV[0]
PAGE = Nokogiri::HTML(open(@url))
@title = PAGE.css('title')[0]

@points = PAGE.search('.subtext > span:first-child')
@item_id = PAGE.search('.subtext > a:nth-child(3)').map {|link| link['href'] }
post = Post.new(@title.text, @url, @points.text, to_split(@item_id, "=")[1])




PAGE.search('.default').map do |font|
  user_name = font.search('.comhead > a:first-child').text
  comment_text = font.search('font:first-child').inner_text

  comment = Comment.new(user_name, comment_text)
  post.add_comment(comment)
end

```

> Showcased above is a simple little webscraper created using the ruby gem Nokogiri. Using this gem I was able to scrape a post on the website HackerNews, and download the html rendering of the page. Implementing standard methods included with the Nokogiri Gem I was able to parse the necessary data needed to convey what I thought to be the relevant information about the post and its commenters.