<script>
  import { TextField, Row, Col } from 'sveltfy/src';
</script>

<Row>
  <Col>
    <TextField disabled value="Hello">Regular</TextField>
    <TextField disabled filled value="Hello">Filled</TextField>
    <TextField disabled outlined value="Hello">Outlined</TextField>
    <TextField disabled solo value="Hello" />
  </Col>
  <Col>
    <TextField readonly value="Hello">Regular</TextField>
    <TextField readonly filled value="Hello">Filled</TextField>
    <TextField readonly outlined value="Hello">Outlined</TextField>
    <TextField readonly solo value="Hello" />
  </Col>
</Row>
