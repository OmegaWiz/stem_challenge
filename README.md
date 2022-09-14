# MVIS

[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]

MWIT Very Intelligent System (prototype).

This project is part of the course in Mahidol Wittayanusorn School.

[View Demo](https://mwit30-8.github.io/MVIS/)
·
[Report Bug](https://github.com/mwit30-8/MVIS/issues)
·
[Request Feature](https://github.com/mwit30-8/MVIS/issues)

## Dependencies

- [Yarn](https://yarnpkg.com/)
- [Docker Compose](https://docs.docker.com/compose/)

## Getting Started

1. Clone the repo

   ```sh
   git clone https://github.com/OmegaWiz/stem_challenge
   cd stem_challenge
   ```

2. Run DGraph locally at <http://localhost:8080/graphql>

   1. Change directory to `/backend`

      ```sh
      cd backend
      ```

   2. Build and run

      ```sh
      docker compose build # Build docker images
      docker compose up # Run DGraph
      # or
      docker compose up --build # Build and Run docker images
      ```

      Use `--wait` flag to run in background.

   3. Shutdown DGraph

      Only run when run DGraph in background and done working with DGraph.

      ```sh
      docker compose down --volumes
      ```

3. Deploy graphql schema and lambda script

   1. Change directory to `/backend`

      ```sh
      cd backend
      ```

   2. Set environmental variable

      - `AUTH0_CLIENT_ID` and `AUTH0_DOMAIN`

      You may define the variable in `/backend/.env`.

      If you are deploying to DGraph Cloud, there are additional variables to be set.

      - `CEREBRO_JWT` or both `CEREBRO_EMAIL` and `CEREBRO_PASSWORD`
      - `DEPLOYMENT_NAME`

   3. Install dependencies

      ```sh
      yarn install
      ```

   4. Build and deploy

      ```sh
      yarn build # deploy to local DGraph
      ```

      or

      ```sh
      yarn deploy # deploy to DGraph Cloud
      ```

4. Run frontend application

   1. Change directory to `/frontend`

      ```sh
      cd frontend
      ```

   2. Set environmental variable

      - `AUTH0_CLIENT_ID` and `AUTH0_DOMAIN`
      - `BACKEND_URL` (Usually <http://localhost:8080/graphql> for local DGraph)
      - `BACKEND_API_KEY` (may be required by DGraph Cloud)

      You may define the variable in `/frontend/.env`.

   3. Install dependencies

      ```sh
      yarn install
      ```

   4. Build graphql code

      This must be re-run every time the schema, queries, and/or mutations change.

      ```sh
      yarn codegen
      ```

   5. Run Expo dev client

      This will automatically watches over changes in `/frontend/src`.

      ```sh
      yarn start
      ```

      If you want to run [storybook](https://storybook.js.org/) to test each component,
      run the following 2 commands concurrently.

      1. Run storybook server (Optional).
         ```sh
         yarn storybook
         ```
      2. Run Expo dev client.
         ```sh
         yarn start:storybook
         ```

## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".
Don't forget to give the project a star! Thanks again!

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

Distributed under the MIT License. See `LICENSE` for more information.

[contributors-shield]: https://img.shields.io/github/contributors/mwit30-8/MVIS.svg?style=for-the-badge
[contributors-url]: https://github.com/mwit30-8/MVIS/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/mwit30-8/MVIS.svg?style=for-the-badge
[forks-url]: https://github.com/mwit30-8/MVIS/network/members
[stars-shield]: https://img.shields.io/github/stars/mwit30-8/MVIS.svg?style=for-the-badge
[stars-url]: https://github.com/mwit30-8/MVIS/stargazers
[issues-shield]: https://img.shields.io/github/issues/mwit30-8/MVIS.svg?style=for-the-badge
[issues-url]: https://github.com/mwit30-8/MVIS/issues
[license-shield]: https://img.shields.io/github/license/mwit30-8/MVIS.svg?style=for-the-badge
[license-url]: https://github.com/mwit30-8/MVIS/blob/develop/LICENSE
