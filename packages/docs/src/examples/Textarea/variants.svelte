<script>
  import { Row, Col, Textarea } from 'sveltfy/src';
</script>

<Row>
  <Col>
    <Textarea>Regular</Textarea>
    <Textarea filled>Filled</Textarea>
  </Col>
  <Col>
    <Textarea outlined>Outlined</Textarea>
    <Textarea solo placeholder="Solo" />
  </Col>
</Row>
