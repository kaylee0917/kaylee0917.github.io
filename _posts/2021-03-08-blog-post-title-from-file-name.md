---
title: "Post 1 title"
layout: post
categories: [Python Programming]
---
## First Blog Post Title
Blog Post Title From First Header

Due to a plugin called `jekyll-titles-from-headings` which is supported by GitHub Pages by default. The above header (in the markdown file) will be automatically used as the pages title.

If the file does not start with a header, then the post title will be derived from the filename.

This is a sample blog post. You can talk about all sorts of fun things here.

---

### This is a header

#### Some T-SQL Code

```tsql
SELECT This, [Is], A, Code, Block -- Using SSMS style syntax highlighting
    , REVERSE('abc')
FROM dbo.SomeTable s
    CROSS JOIN dbo.OtherTable o;
    
def get_difference_52wk_vs_price(ticker):
    changes=[]
    end = datetime.datetime.now()
    start = end - datetime.timedelta(weeks=52)
    
    for k in range(len(ticker)):
        df = web.DataReader(ticker[k], 'yahoo', start, end)
        df = df.reset_index()
    
        highest_high = df['High'].max()
        current_price = float(df[df['Date'] == '2021-12-27']['Adj Close'])
        changes.append((1-current_price/highest_high)*100)
        
    data = {'stock': ticker, 'change': changes}
    change_df = pd.DataFrame(data, columns=['stock', 'change'])
    
    return change_df
    
```

#### Some PowerShell Code

```powershell
Write-Host "This is a powershell Code block";

# There are many other languages you can use, but the style has to be loaded first

ForEach ($thing in $things) {
    Write-Output "It highlights it using the GitHub style"
}

def get_difference_52wk_vs_price(ticker):
    changes=[]
    end = datetime.datetime.now()
    start = end - datetime.timedelta(weeks=52)
    
    for k in range(len(ticker)):
        df = web.DataReader(ticker[k], 'yahoo', start, end)
        df = df.reset_index()
    
        highest_high = df['High'].max()
        current_price = float(df[df['Date'] == '2021-12-27']['Adj Close'])
        changes.append((1-current_price/highest_high)*100)
        
    data = {'stock': ticker, 'change': changes}
    change_df = pd.DataFrame(data, columns=['stock', 'change'])
    
    return change_df
```
