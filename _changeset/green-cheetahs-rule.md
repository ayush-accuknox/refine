---
"@refinedev/chakra-ui": minor
---

-   `RefineThemes` added. It contains predefined colors for the chakra-UI components.

```tsx
import { Refine } from "@refinedev/core";
import { RefineThemes } from "@refinedev/chakra-ui";
import dataProvider from "@refinedev/simple-rest";
const App = () => {
    // ---
    return (
        <ChakraProvider theme={RefineThemes.Magenta}>
            <Refine dataProvider={dataProvider("YOUR_API_URL")}>
                {/** your app here */}
            </Refine>
        </ChakraProvider>
    );
};
```

-   default title with icon added to `AuthPage`. It uses `ThemedTitle` component from `@refinedev/chakra-ui`. You can remove it by setting `title` prop to `false`.

```tsx
import { AuthPage, ThemedTitle } from "@refinedev/chakra-ui";

const MyLoginPage = () => {
    return (
        <AuthPage
            type="login"
            title={
                <ThemedTitle
                    title="My Title"
                    icon={<img src="https://refine.dev/img/logo.png" />}
                />
            }
        />
    );
};
```

-   `title` prop added to `AuthPage`'s `renderContent` prop to use in the custom content.

```tsx
import { AuthPage } from "@refinedev/chakra-ui";
import { Box, Heading } from "@chakra-ui/react";

const MyLoginPage = () => {
    return (
        <AuthPage
            contentProps={{
                style: {
                    width: "400px",
                },
            }}
            renderContent={(
                content: React.ReactNode,
                title: React.ReactNode,
            ) => {
                return (
                    <Box
                        bg="white"
                        borderRadius="md"
                        px="5"
                        display="flex"
                        flexDirection="column"
                        justifyContent="center"
                        alignItems="center"
                    >
                        <Heading color="white">Extra Header</Heading>
                        {content}
                        <Heading color="white">Extra Footer</Heading>
                    </Box>
                );
            }}
        />
    );
};
```

-   `<ThemedLayout>`, `<ThemedSider>`, `<ThemedTitle>`, `<ThemedHeader>` created to use theme colors.

-   `<EditButton>` in `<Show>` color changed to `brand`.
-   `<CreateButton>` color changed to `brand`.

-   `<AuthPage>` component uses colors from the theme.
-   `<AuthPageTitle>` added to `AuthPage`