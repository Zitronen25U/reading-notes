# Class 38 Reading Notes

## Assets MetaData and CSS

### Assets

- next can serve static assets under the hood

#### Download Your Profile Picture

1. Download your profile picture in .jpg format (or use this file).

2. Create an images directory inside of the public directory.

3. Save the picture as profile.jpg in the public/images directory.

4. The image size can be around 400px by 400px.

5. You may remove the unused SVG logo file directly under the public directory.

### MetaData

- how can we modiy things like a ```<title>``` tag?

- ```<title>``` is part of a ```<head>``` tag

```js
<Head>
  <title>Create Next App</title>
  <link rel="icon" href="/favicon.ico" />
</Head>
```

- in next, a capitol Head tag is used

- allows you to modify the lowercase head tag of the page

### CSS Styling

- you can import CSS Libraries, like tailwinds

#### Layout Components

```js
export default function Layout({ children }) {
  return <div>{children}</div>
}
```

```js
import Head from 'next/head'
import Link from 'next/link'
import Layout from '../../components/layout'

export default function FirstPost() {
  return (
    <Layout>
      <Head>
        <title>First Post</title>
      </Head>
      <h1>First Post</h1>
      <h2>
        <Link href="/">
          <a>Back to home</a>
        </Link>
      </h2>
    </Layout>
  )
}
```

#### Global Styles

- global styles can be applied to the _app page