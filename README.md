# Canadadrives FE Technical

## Build Setup

```bash
# pull down a copy locally
git clone https://github.com/jcontheweb/canadadrives.git

# install dependencies
$ yarn install

# serve with hot reload at localhost:3000
$ yarn dev

# build for production and launch server
$ yarn build
$ yarn start

# generate static project
$ yarn generate
```

## Technologies Used

- VueJS (Nuxt SPA to save time on handling routes)
- Axios
- TailwindCSS (Allows for rapid prototyping)

## Component Structure Breakdown
Each component has a _Component_ Container which should handle all necessary data fetching for the component, leaving it's Child components very slim and straight to the point.