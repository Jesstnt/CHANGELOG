# Lorem Ipsum


## What is Lorem Ipsum?

**Lorem Ipsum** is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

![image](/image/mock.avif)


## Where does it come from?


The first step would be to create an API key. You can follow the [Notions Getting Started Guide](https://developers.notion.com/docs/getting-started) where we will be able to generate a new API key, which we will need for the `env` file as `NOTION_SECRET`

![Untitled](/image/Untitled.png)

For posting new blog articles, I already made a template, so we can simply duplicate it and start writing articles. (Don’t forget to connect your notion page to your integration!)

**Template**: [https://www.notion.so/phung/c5d4aa9aa08745ccb45afd24537fcf28](https://www.notion.so/de4b35cf6df5404c901892b6df7244b4?pvs=21)

![Untitled](/image/Untitled%20(1).png)

Once we cloned the blog template, we need `DATABASE_ID` which can be taken from the URL. It is the id after `xxx.notion.site/`

![Untitled](/image/Untitled%20\(2.png)

### Forking the codebase

[Click here](https://github.com/tuanphungcz/nextjs-notion-blog-starter/fork) to fork the code base and pull the repository

```bash
npm install && npm run
```

The first time you run the blog, you will get an error of missing API key, that’s because we haven't updated the `.env` file.

![Untitled](/image/Untitled%20(2).png)

The last thing we need to do to make the blog work is to rename `.env.example` to `env` and update the variables

```bash
# Notion secret integration
NOTION_SECRET=
# Database id from cloned template
BLOG_DATABASE_ID=

# Convertkit subscription (Optional)
NEXT_PUBLIC_CONVERTKIT_FORM_ID=
NEXT_PUBLIC_CONVERTKIT_API_KEY=

# Umami analytics (Optional)
UMAMI_ID=
```

If we did everything right, we should be able to see the working blog 🎉

![Untitled](/image/Untitled%20(3).png)
