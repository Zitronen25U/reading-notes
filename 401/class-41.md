# Class 41 Reading Notes

## Next JS Dynamic Routes

### How to statically generate pages with dynamic routes

```js
import Layout from '../../components/layout'

export default function Post() {
  return <Layout>...</Layout>
}

```

```js
import Layout from '../../components/layout'

export default function Post() {
  return <Layout>...</Layout>
}

export async function getStaticPaths() {
  // Return a list of possible value for id
}
```

```js
import Layout from '../../components/layout'

export default function Post() {
  return <Layout>...</Layout>
}

export async function getStaticPaths() {
  // Return a list of possible value for id
}

export async function getStaticProps({ params }) {
  // Fetch necessary data for the blog post using params.id
}
```

#### Impliment get static paths

- Create a file called [id].js inside the pages/posts directory

```js
mport Layout from '../../components/layout'

export default function Post() {
  return <Layout>...</Layout>
}
```

```js
export function getAllPostIds() {
  const fileNames = fs.readdirSync(postsDirectory)

  // Returns an array that looks like this:
  // [
  //   {
  //     params: {
  //       id: 'ssg-ssr'
  //     }
  //   },
  //   {
  //     params: {
  //       id: 'pre-rendering'
  //     }
  //   }
  // ]
  return fileNames.map(fileName => {
    return {
      params: {
        id: fileName.replace(/\.md$/, '')
      }
    }
  })
}
```

## Deploying your next.js app

### Push to Github

### Deploy to Vercel (or anything I guess)

- You’ll need to Install Vercel for GitHub

- vercel is created by next.js, and has direct support for next

- you can preview deployments for every push

### Develop, Preview, Ship

- Develop: We’ve written code in Next.js and used the Next.js development server running to take advantage of its hot reloading feature.

- Preview: We’ve pushed changes to a branch on GitHub, and Vercel created a preview deployment that’s available via a URL. We can share this preview URL with others for feedback. In addition to doing code reviews, you can do deployment previews.

- Ship: We’ve merged the pull request to main to ship to production.

