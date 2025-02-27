# Copyright (c) 2010-2022, Lawrence Livermore National Security, LLC. Produced
# at the Lawrence Livermore National Laboratory. All Rights reserved. See files
# LICENSE and NOTICE for details. LLNL-CODE-806117.
#
# This file is part of the MFEM library. For more information and source code
# availability visit https://mfem.org.
#
# MFEM is free software; you can redistribute it and/or modify it under the
# terms of the BSD-3 license. We welcome feedback and contributions, see file
# CONTRIBUTING.md for details.

set(SRCS
  bilinearform.cpp
  bilinearform_ext.cpp
  bilininteg.cpp
  bilininteg_br2.cpp
  bilininteg_convection_mf.cpp
  bilininteg_convection_pa.cpp
  bilininteg_convection_ea.cpp
  bilininteg_dgtrace_pa.cpp
  bilininteg_dgtrace_ea.cpp
  bilininteg_diffusion_mf.cpp
  bilininteg_diffusion_pa.cpp
  bilininteg_diffusion_ea.cpp
  bilininteg_divergence.cpp
  bilininteg_hcurl.cpp
  bilininteg_hdiv.cpp
  bilininteg_vectorfe.cpp
  bilininteg_gradient.cpp
  bilininteg_mass_mf.cpp
  bilininteg_mass_pa.cpp
  bilininteg_mass_ea.cpp
  bilininteg_transpose_ea.cpp
  bilininteg_vecdiffusion.cpp
  bilininteg_vecdiffusion_mf.cpp
  bilininteg_vecmass.cpp
  bilininteg_vecmass_mf.cpp
  coefficient.cpp
  complex_fem.cpp
  convergence.cpp
  datacollection.cpp
  doftrans.cpp
  eltrans.cpp
  estimators.cpp
  fe.cpp
  fe/fe_base.cpp
  fe/fe_fixed_order.cpp
  fe/fe_h1.cpp
  fe/fe_l2.cpp
  fe/fe_nd.cpp
  fe/fe_nurbs.cpp
  fe/fe_pos.cpp
  fe/fe_rt.cpp
  fe/fe_ser.cpp
  fe_coll.cpp
  fespace.cpp
  geom.cpp
  gridfunc.cpp
  hybridization.cpp
  intrules.cpp
  ceed/algebraic.cpp
  ceed/full-assembly.cpp
  ceed/solvers-atpmg.cpp
  ceed/convection.cpp
  ceed/diffusion.cpp
  ceed/nlconvection.cpp
  ceed/mass.cpp
  ceed/operator.cpp
  ceed/util.cpp
  linearform.cpp
  lininteg.cpp
  multigrid.cpp
  nonlinearform.cpp
  nonlinearform_ext.cpp
  nonlininteg.cpp
  fespacehierarchy.cpp
  nonlininteg_vectorconvection.cpp
  nonlininteg_vectorconvection_mf.cpp
  qinterp/det.cpp
  qinterp/eval_by_nodes.cpp
  qinterp/eval_by_vdim.cpp
  qinterp/grad_by_nodes.cpp
  qinterp/grad_by_vdim.cpp
  qinterp/grad_phys_by_nodes.cpp
  qinterp/grad_phys_by_vdim.cpp
  quadinterpolator.cpp
  quadinterpolator_face.cpp
  restriction.cpp
  staticcond.cpp
  tmop.cpp
  tmop/tmop_pa.cpp
  tmop/tmop_pa_da3.cpp
  tmop/tmop_pa_h2d.cpp
  tmop/tmop_pa_h2d_c0.cpp
  tmop/tmop_pa_h2m.cpp
  tmop/tmop_pa_h2m_c0.cpp
  tmop/tmop_pa_h2s.cpp
  tmop/tmop_pa_h2s_c0.cpp
  tmop/tmop_pa_h3d.cpp
  tmop/tmop_pa_h3d_c0.cpp
  tmop/tmop_pa_h3m.cpp
  tmop/tmop_pa_h3m_c0.cpp
  tmop/tmop_pa_h3s.cpp
  tmop/tmop_pa_h3s_c0.cpp
  tmop/tmop_pa_jp2.cpp
  tmop/tmop_pa_jp3.cpp
  tmop/tmop_pa_p2.cpp
  tmop/tmop_pa_p2_c0.cpp
  tmop/tmop_pa_p3.cpp
  tmop/tmop_pa_p3_c0.cpp
  tmop/tmop_pa_tc2.cpp
  tmop/tmop_pa_tc3.cpp
  tmop/tmop_pa_w2.cpp
  tmop/tmop_pa_w2_c0.cpp
  tmop/tmop_pa_w3.cpp
  tmop/tmop_pa_w3_c0.cpp
  tmop_tools.cpp
  tmop_amr.cpp
  gslib.cpp
  transfer.cpp
  lor.cpp
  )

set(HDRS
  bilinearform.hpp
  bilinearform_ext.hpp
  bilininteg.hpp
  coefficient.hpp
  complex_fem.hpp
  convergence.hpp
  datacollection.hpp
  doftrans.hpp
  eltrans.hpp
  estimators.hpp
  fe.hpp
  fe/fe_base.hpp
  fe/fe_fixed_order.hpp
  fe/fe_h1.hpp
  fe/fe_l2.hpp
  fe/fe_nd.hpp
  fe/fe_nurbs.hpp
  fe/fe_pos.hpp
  fe/fe_rt.hpp
  fe/fe_ser.hpp
  fe_coll.hpp
  fem.hpp
  fespace.hpp
  geom.hpp
  gridfunc.hpp
  hybridization.hpp
  intrules.hpp
  ceed/algebraic.hpp
  ceed/full-assembly.hpp
  ceed/solvers-atpmg.hpp
  ceed/coefficient.hpp
  ceed/convection.hpp
  ceed/diffusion.hpp
  ceed/integrator.hpp
  ceed/mass.hpp
  ceed/nlconvection.hpp
  ceed/operator.hpp
  ceed/util.hpp
  linearform.hpp
  lininteg.hpp
  multigrid.hpp
  nonlinearform.hpp
  nonlinearform_ext.hpp
  nonlininteg.hpp
  qinterp/dispatch.hpp
  qinterp/eval.hpp
  qinterp/grad.hpp
  quadinterpolator.hpp
  quadinterpolator_face.hpp
  restriction.hpp
  fespacehierarchy.hpp
  staticcond.hpp
  tbilinearform.hpp
  tbilininteg.hpp
  tcoefficient.hpp
  teltrans.hpp
  tevaluator.hpp
  tfe.hpp
  tfespace.hpp
  tintrules.hpp
  tmop.hpp
  tmop/tmop_pa.hpp
  tmop_tools.hpp
  tmop_amr.hpp
  gslib.hpp
  transfer.hpp
  lor.hpp
  )

if (MFEM_USE_SIDRE)
  list(APPEND SRCS sidredatacollection.cpp)
  list(APPEND HDRS sidredatacollection.hpp)
endif()

if (MFEM_USE_CONDUIT)
  list(APPEND SRCS conduitdatacollection.cpp)
  list(APPEND HDRS conduitdatacollection.hpp)
endif()

if (MFEM_USE_ADIOS2)
  list(APPEND SRCS adios2datacollection.cpp)
  list(APPEND HDRS adios2datacollection.hpp)
endif()

if (MFEM_USE_FMS)
  list(APPEND SRCS fmsdatacollection.cpp fmsconvert.cpp)
  list(APPEND HDRS fmsdatacollection.hpp fmsconvert.hpp)
endif()

if (MFEM_USE_MPI)
  list(APPEND SRCS
    pbilinearform.cpp
    pfespace.cpp
    pgridfunc.cpp
    plinearform.cpp
    pnonlinearform.cpp
    prestriction.cpp)
  # If this list (HDRS -> HEADERS) is used for install, we probably want the
  # headers added all the time.
  list(APPEND HDRS
    pbilinearform.hpp
    pfespace.hpp
    pgridfunc.hpp
    plinearform.hpp
    pnonlinearform.hpp
    prestriction.hpp)
endif()

convert_filenames_to_full_paths(SRCS)
convert_filenames_to_full_paths(HDRS)

set(SOURCES ${SOURCES} ${SRCS} PARENT_SCOPE)
set(HEADERS ${HEADERS} ${HDRS} PARENT_SCOPE)
