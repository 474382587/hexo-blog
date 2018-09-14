Use this plugin to extract CSS file from compiled js file. (Production)
Or use style-loader for Dev environment

```
const env = process.env.NODE_ENV || 'development'
...
{
    test: /\.(scss|css)$/,
    use: env === 'production' 
      ? extractSASS.extract({
          fallback: 'style-loader',
          use: ['css-loader','sass-loader']
        })
      : [ 'style-loader', 'css-loader', 'sass-loader' ]
}
```
