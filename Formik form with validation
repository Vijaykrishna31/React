import React from 'react';
import 'bootstrap/dist/css/bootstrap.min.css';
import 'bootstrap/dist/js/bootstrap.bundle.min';
import { Formik, Form, Field, ErrorMessage } from 'formik';
import './App.css'
const App = () => {
  const handleSubmit = (values, { setSubmitting, resetForm }) => {
    setTimeout(() => {
      console.log(values);
      alert(JSON.stringify(values, null, 20));
      setSubmitting(false);
      resetForm();
    }, 400);
  };

  return (
    <>
      <Formik
        initialValues={{ email: "", password: "" }}
        validate={(values) => {
          const errors = {};

          if (!values.email) {
            errors.email = "*Email is Required";
          } else if (
            !/^[A-Z0-9._%+-]+@[A-Z0-9.-]+\.[A-Z]{2,}$/i.test(values.email)
          ) {
            errors.email = "Invalid email address";
          }
          if (!values.password) {
            errors.password = "*Password is Required";
          }else if (values.password.length<8 ) {
            errors.password = "Please must be atleast 8 characters";
          }
          return errors;
        }}
        onSubmit={handleSubmit}
      >
        {({ isSubmitting, resetForm }) => (
          <section class="vh-100 gradient-custom">

            <div class="container py-5 h-100">
              <div class="row d-flex justify-content-center align-items-center h-100">
                <div class="col-12 col-md-8 col-lg-6 col-xl-5">
                  <div class="card bg-dark text-white" >
                    <div class="card-body p-5 text-center">
                      <h2 class="fw-bold mb-4 text-uppercase text-primary">Login</h2>

                      <Form>
                        <div data-mdb-input-init class="form-outline form-white mb-4 ">
                          <Field
                            type="email"
                            name="email"
                            placeholder="Enter email address"
                            class="form-control form-control-lg"
                          />
                          <ErrorMessage name="email" component="span" class="text-danger fw-bold" /></div>

                        <div data-mdb-input-init class="form-outline form-white mb-4">
                          <Field type="password" name="password" placeholder="Password" class="form-control form-control-lg" />
                          <ErrorMessage name="password" component="span" class="text-danger fw-bold" /></div>

                          <button data-mdb-button-init data-mdb-ripple-init class="btn btn-primary btn-lg btn-block px-5" type="submit" disabled={isSubmitting}>Login</button>

                      </Form>
                    </div></div></div></div></div>
          </section>
        )}
      </Formik>
    </>
  );
};

export default App;
