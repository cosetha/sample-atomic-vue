<template>
  <div class="container mx-auto">
    <div class="grid grid-cols-3 gap-4">
      <div class="my-2">
        <h2 class="my-2 bg-green-500 text-white px-6 py-2">Atoms</h2>
        <h2 class="my-2 bg-teal-500 px-6 py-2">Paragraph</h2>
        <Paragraf align="left">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis in
          magnam pariatur natus itaque consequuntur dolores praesentium, aut
          sequi voluptate.
          <span class="bg-blue-500 px-6 py-2 inline-block">Left</span>
        </Paragraf>
        <Paragraf align="right">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis in
          magnam pariatur natus itaque consequuntur dolores praesentium, aut
          sequi voluptate.
          <span class="bg-blue-500 px-6 py-2 inline-block">Right</span>
        </Paragraf>
        <Paragraf align="center">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis in
          magnam pariatur natus itaque consequuntur dolores praesentium, aut
          sequi voluptate.
          <span class="bg-blue-500 px-6 py-2 inline-block">Center</span>
        </Paragraf>
        <br />
        <h2 class="my-2 bg-teal-500 px-6 py-2">Button</h2>
        <Button label="Button" variant="danger" class="my-2">Danger</Button>
        <br />
        <Button label="Button" variant="primary" class="my-2">Primary</Button>
        <br />
        <Button label="Button" variant="secondary" class="my-2"
          >Secondary</Button
        >
        <br />
        <Button label="Button" variant="warning" class="my-2">warning</Button>
        <br />
        <Button label="Button" variant="success" class="my-2">Success</Button>
        <br />
        <Button label="Button" variant="tertiary" class="my-2">tertiary</Button>
        <h2 class="my-2 bg-teal-500 px-6 py-2">Button Size</h2>
        <Button label="Button" variant="secondary" size="sm" class="my-2 mx-2"
          >Secondary Small</Button
        >
        <Button label="Button" variant="secondary" class="my-2 mx-2"
          >Secondary Default</Button
        >
        <Button label="Button" variant="secondary" size="lg" class="my-2"
          >Secondary Large</Button
        >
        <h2 class="my-2 bg-teal-500 px-6 py-2">Link</h2>
        <Link
          path="/about"
          label="Link Light"
          type="light"
          v-bind:isDisabled="false"
        />
        <Link
          path="/about"
          label="Link Dark"
          type="dark"
          v-bind:isDisabled="false"
        />
        <Link
          path="/about"
          label="Link Disabled"
          type="dark"
          v-bind:isDisabled="true"
        />
      </div>
      <!-- ... -->
      <div>
        <div class="my-2">
          <h2 class="my-2 bg-green-500 text-white px-6 py-2">Molecules</h2>
          <h2 class="my-2 bg-teal-500 px-6 py-2">Link List</h2>
          <div class="block flex-grow lg:flex lg:items-center lg:w-auto">
            <LinkList :links="links" />
          </div>
        </div>
      </div>
      <div>
        <div class="my-2">
          <h2 class="my-2 bg-green-500 text-white px-6 py-2">Organism</h2>
          <h2 class="my-2 bg-teal-500 px-6 py-2">Navigation</h2>
          <Navigation></Navigation>
          <h2 class="my-2 bg-teal-500 px-6 py-2">Card</h2>
          <Card class="my-2">
            <h2>Default Card</h2>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipisicing elit. Alias
              sit perspiciatis laboriosam doloribus, aliquam, porro quasi
              reiciendis.
            </p>
          </Card>
          <Card header="Card with Header" class="my-2">
            <p>
              Lorem ipsum dolor sit amet, consectetur adipisicing elit. Adipisci
              ab vitae, facilis. Blanditiis fugiat ducimus, consectetur dolorum!
              Ea nisi, corporis laborum, numquam in, dolores maxime odio
              possimus similique voluptas officia?
            </p>
          </Card>
          <Card header="Card with a footer" class="my-2">
            <p>
              Lorem ipsum dolor sit amet, consectetur adipisicing elit. Adipisci
              ab vitae, facilis. Blanditiis fugiat ducimus, consectetur dolorum!
              Ea nisi, corporis laborum, numquam in, dolores maxime odio
              possimus similique voluptas officia?
            </p>
            <template v-slot:footer>
              <div class="flex justify-between">
                <Button size="sm" variant="tertiary">Cancel</Button>
                <Button size="sm" variant="primary">Download</Button>
              </div>
            </template>
          </Card>
        </div>
      </div>
      <div>9</div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Button from '../components/atoms/Button';
import Paragraf from '../components/atoms/Paragraph';
import Link from '../components/atoms/Link';
import LinkList from '../components/molecules/LinkList';
import Card from '../components/organism/Card';
import Navigation from '../components/organism/Navigation';
export default {
  name: 'Home',
  components: { Button, Link, Card, Navigation, Paragraf, LinkList },
  data() {
    return {
      links: [
        {
          path: '/',
          label: 'Index'
        },
        {
          path: '/atoms',
          label: 'Atoms'
        },
        {
          path: '/molecules',
          label: 'Molecules'
        },
        {
          path: '/organisms',
          label: 'Organisms'
        }
      ]
    };
  }
};
</script>
