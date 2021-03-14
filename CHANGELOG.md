# 1.2.9 (12/03/2021)

-   Fixed #2: operator _short-circuiting_ caused only one error to be set when using `form.setErrors`.

# 1.2.8 (12/03/2021)

-   Object constraint on form type parameter, string constraint on error type parameter. (`FormState<T extends object, State, Error extends string>`)
-   React 17 support (#1)
-   `form.setErrors` should now be working correctly.
-   Custom error types are now correctly inferred from `useForm`:

    ```
    type Language = "error-email" | "error-password"

    const form = useForm({email: "test@gmail.com", password: ""}, yupValidator(schema, {}, (message) => message as Language));

    form.setError("email", ...); // Must be "error-email" | "error-password"
    ```