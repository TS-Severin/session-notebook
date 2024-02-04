# react data fetch

### swr-library

=> prevents that the dta is fetched always again

```js
const fetcher = (...args) => fetch(...args).then(res => res.json())

import useSWR from "swr";

// the swr hook can return a lot of data e. g. data, error etc.

const {data, error, isValidating} = useSWR(`url${}`, fetch)
```

=> it chaches the data in the browser cache an uses it => so something which already has been loaded is revalidated but that is much faster

in App.js:

```js
import GlobalStyle from "../styles";
import { SWRConfig } from "swr";

const fetcher = (url) => fetch(res).then((res) => res.json());

export default function App({ Component, pageProps }) {
  return (
    <>
      <GlobalStyle />
      <Component
        {...pageProps}
        // now we can use the fetcher in every component
        value={{ fetcher }}
      />
    </>
  );
}
```

### SWR is a global configuration

=> once applied it can be used everywhere
