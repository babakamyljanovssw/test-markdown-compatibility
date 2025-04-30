# Repo to test different Markdown syntaxes for SSW.Rules migration

**PBI - https://github.com/SSWConsulting/SSW.Rules/issues/1713**

## Steps

1. Run `pnpm run dev`
2. Go to post - http://localhost:3000/posts/test-markdown-compatibility

**Report**

Ttested different markdown syntaxes using latest TinaCMS starter kit for Next.js with TinaMarkdown.

1. ✅ Strikethrough - it is working as expected with one `~` and double `~~` tilda

![Image](https://github.com/user-attachments/assets/03d274c8-e31d-4125-b9a8-8dcbd7ea4268)
**Figure: Strikethroughs are rendered correctly**

2. Image embeds:

- ✅ Image embed with the relative URL works correctly
- ❌ Image embed with internet URL is treated as the link and doesn't render the image

![Image](https://github.com/user-attachments/assets/34ba3a8e-9d40-4dcc-a9c4-e3a62d2a30f3)
**Figure: Image embed works with relative URLs but not with internet URLs**

3. ❌ List inside Blockquotes - using list after blockquote makes the whole page to be rendered as code block.

![Image](https://github.com/user-attachments/assets/5cbce4bb-ddf6-4461-ba12-c2564bfa8cdf)
**Figure: Using list with blockquote fails**

4. ❌ Shortcode Tag - using it makes the whole page to be rendered as code block also.

![Image](https://github.com/user-attachments/assets/bb7ded1d-911e-4967-a253-a2e021bd536e)
**Figure: Using Shortcode tag fails**

Based on this we can start work on these issues individually and create custom components for TinaMarkdown:

- https://github.com/SSWConsulting/SSW.Rules/issues/1545
- https://github.com/SSWConsulting/SSW.Rules/issues/1546
- https://github.com/SSWConsulting/SSW.Rules/issues/1548

And we can close strikethrough issue as TinaMarkdown successfully rendering it:

- https://github.com/SSWConsulting/SSW.Rules/issues/1547
